<template>
  <section class="content-container">
    <agile
      :infinite="false"
      :navButtons="false"
      :dots="false"
      :slidesToShow="1"
      :centerMode="true"
      @after-change="onSlideChange"
    >
      <div class="slide">
        <img src="@/assets/UNU_DAY_mobile.jpg" alt="">
        <h3>Atemraubendes Fahrerlebnis</h3>
        <p>
          Im null Komma nichts erreichst du deine Geschwindigkeit. So bist du immer besonders schnell am Ziel und nichts kann dich aufhalten.
        </p>
      </div>
      <div class="slide">
        <img src="@/assets/UNU_NIGHT_mobile.jpg" alt="">
        <h3>Bei Tag und Nacht</h3>
        <p>
          Egal zu welcher Tageszeit oder bei welchem Wetter, du bist immer komfortabel und sicher unterwegs. So holst du dir dein außergewöhnliches Stadt Erlebnis zurück.
        </p>
      </div>
    </agile>
  </section>
  <div class="pagination">
    <div v-if="currentSlide == 0" class="left"></div>
    <div v-if="currentSlide == 1" class="right"></div>
  </div>
</template>

<script>
import { VueAgile } from 'vue-agile'


  export default {
    components: {
      agile: VueAgile,
    },
    data() {
      return {
        currentSlide: 0,
      }
    },
    methods: {
      onSlideChange(e) {
        this.currentSlide = e.currentSlide;
      }
    },
    setup() {
      // eslint-disable-next-line no-unused-vars
      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      return {
        onSwiper,
      };
    },
  };
</script>

<style lang="scss" scoped>
.content-container {
  padding-top: 2rem;
  padding-bottom: 2rem;
  .slide {
    height: 100%;
    // min-height: 80vh;
    img {
      margin-bottom: 2rem;
      width: 100%;
    }
  }
}
.pagination {
  height: 3px;
  width: 100%;
  background: lightgrey;
  margin-bottom: 3rem;
  position: relative;
  .left {
    position: absolute;
    top: 0;
    left: 0;
    height: 3px;
    width: 50%;
    background: #C53C2E;
  }
  .right {
    position: absolute;
    top: 0;
    right: 0;
    height: 3px;
    width: 50%;
    background: #C53C2E;
  }
}
</style>