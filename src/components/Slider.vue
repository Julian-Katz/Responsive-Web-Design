<template>
  <section class="content-container">
    <agile
      :infinite="false"
      :navButtons="false"
      :dots="false"
      :slidesToShow="1"
      :centerMode="true" 
    >
      <div class="slide">
        <img src="../assets/slider_image.png" alt="">
        <h3>Atemberaubende Beschleunigung</h3>
        <p>
          Im null Komma nichts erreichst du deine Geschwindigkeit. Nie mehr  warten auf das was kommt.
        </p>
      </div>
      <div class="slide">
        <img src="../assets/slider_image.png" alt="">
        <h3>Völlig Kantenloses Erlebnis</h3>
        <p>
          Keine Kanten, nichts was dich aufhält. Ein Erlebnis ohne Nachteile, nichts stoppt dich.
        </p>
      </div>
    </agile>
  </section>
</template>

<script>
import { VueAgile } from 'vue-agile'


  export default {
    components: {
      agile: VueAgile,
    },
    setup() {
      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      const onSlideChange = () => {
        console.log('slide change');
      };
      return {
        onSwiper,
        onSlideChange,
      };
    },
  };
</script>

<style lang="scss" scoped>
.content-container {
  padding-top: 2rem;
  padding-bottom: 6rem;
  .slide {
    min-height: 80vh;
    padding-right: 1rem;
    img {
      margin-bottom: 2rem;
      width: 100%;
    }
  }
}
</style>