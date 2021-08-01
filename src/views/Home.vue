<template>
  <div>
    <div class="hero-background" style="">
      <div class="wrapper">
        <Nav></Nav>
        <Hero />
      </div>
    </div>

    <div class="articles">
      <Heading title="Nuestros artículos" />
      <div class="wrapper">
        <div class="articles__section">
          <FilterArticles 
            @filter="getArticles"
          />
          <Loader v-if="isLoader" />
          <div class="card-list" v-else>
            <Card
              v-for="article in articles"
              :title="article.title"
              :content="article.content"
              :image="article.image"
              :key="article.id"
            />
          </div>
        </div>
      </div>
    </div>

    <div class="contanct">
      <Heading title="Contáctanos" />
      <suscribe-news-letter />
    </div>
  </div>
</template>

<script>
import Nav from "../components/Nav";
import Hero from "../components/Hero";
import Card from "../components/Card";
import Heading from "../components/Heading";
import FilterArticles from "../components/FilterArticles";
import SuscribeNewsLetter from "../components/SuscribeNewsLetter";
import Loader from '../components/Loader'
import axios from "axios";

export default {
  components: {
    Card,
    Nav,
    Hero,
    Heading,
    FilterArticles,
    SuscribeNewsLetter,
    Loader
  },
  data() {
    return {
      isLoader: false,
      articles: [],
    };
  },
  mounted() {
    this.getArticles('');
  },
  methods: {
    async getArticles(filter) {
      this.isLoader = true
      const res = await axios.get(
        `https://5eed24da4cbc340016330f0d.mockapi.io/api/articles?filter=${filter}`
      );
      this.articles = res.data
      this.isLoader = false
    },
  },
};
</script>

<style lang="scss">
.hero-background {
  background: url("../assets/hero-background.jpg");
  background-size: cover;
  z-index: -3;
  position: relative;
  height: 805px;
  margin: 0;
  &::after {
    content: "";
    position: absolute;
    bottom: 0;
    height: 100px;
    width: 100%;
    background: linear-gradient(
      0deg,
      #ffffff 0%,
      #ffffff 32.22%,
      rgba(255, 255, 255, 0.71) 61.99%,
      rgba(255, 255, 255, 0.0729167) 93.72%,
      rgba(255, 255, 255, 0) 93.72%
    );
  }
}

.articles {
  margin-bottom: 100px;
  &__section {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 30px;
    @media screen and (max-width: 700px) {
      grid-template-columns: 1fr;
    }
    .card-list {
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
    }
  }
}
</style>
