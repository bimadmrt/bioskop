<template>
    <div class="container">
        <div class="header">
            <h1 class="header-title">KACAFILM</h1>
        </div>
            <div class="movie" v-for="(data, index) in movie" :value="data" :key="index">
                <div class="movie-item" @click="detailfilm(data.id)">
                    <img v-bind:src="data.image" class="img-fluid img-movie" v-bind:alt="data">
                </div>
            </div>
                <div class="footer">
                    <h5>Copyright &copy;2020. Created by Bimasakti. All rights reserved</h5>
                </div>
    </div>
</template>
<script>
import Img1 from '../assets/movie/007.jpg'
import Img2 from '../assets/movie/badboys.jpg'
import Img3 from '../assets/movie/bird.jpg'
import Img4 from '../assets/movie/calling.jpg'
import Img5 from '../assets/movie/bohemian.jpg'
import Img6 from '../assets/movie/grudge.jpg'
import Img7 from '../assets/movie/sonic.jpg'
import Img8 from '../assets/movie/underwater.jpg'

export default {
  data: () => ({
    movie: [
      { id: 1, image: Img1 },
      { id: 2, image: Img2 },
      { id: 3, image: Img3 },
      { id: 4, image: Img4 },
      { id: 5, image: Img5 },
      { id: 6, image: Img6 },
      { id: 7, image: Img7 },
      { id: 8, image: Img8 }
    ]
  }),
  methods: {
    detailfilm (filmId) {
      this.$router.push({ name: 'detail', params: { id: filmId } })
    }
  }
}
</script>
<style scoped>
    .container {
        width: auto;
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-auto-rows: minmax(50px, auto);
    }
    .header {
        padding: 50px;
        grid-column: 1/5;
        background-color: #c4c3b5;
        color: #fff;
        text-align: left;
    }
    .header-title {
      font-family: monospace;
      font-size: 70px;
      color: #deda9e;
    }
    .header-subtitle {
        font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
        font-size: 20px;
        color: #bd3434ea;
    }
    .footer {
        padding: 10px;
        grid-column: 1/5;
        background-color: #c4c3b5;
        color: black;
        text-align: center;
    }
    .movie {
        padding-top: 60px;
        padding-bottom: 60px;
        text-align: center;
        background-color: #ededed;
    }
    .img-movie {
        width: 250px;
        box-shadow: 0 20px 35px 0 rgba(0,0,0,0.2);
        transition: 0.3s ease;
    }
    .img-movie:hover{
        box-shadow: 0 40px 45px 0 rgba(0,0,0,0.2);
    }
    .example-slide {
    align-items: center;
    background-color: #666;
    color: #999;
    display: flex;
    font-size: 1.5rem;
    justify-content: center;
    min-height: 10rem;
  }
</style>
