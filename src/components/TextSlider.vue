<template>
  <section class="content-container">
    <div class="text">
      <p>Pressestimmen</p>
    </div>
    <agile
      ref="slider"
      :infinite="false"
      :navButtons="false"
      :dots="false"
      :autoplay="true"
      :autoplaySpeed="5000"
      :pauseOnHover="false"
    >
      <div class="slide">
        <h3>
          „Unu-Ellipsoid im Test: Die urbane Revolution“ (der Spiegel)
        </h3>
      </div>
      <div class="slide">
        <h3>
          „Unu-Ellipsoid: Warum nicht schon früher“ (Der Standard)
        </h3>
      </div>
      <div class="slide">
        <h3>
          „Unu-Ellipsoid: Design und Ingenieurskunst - krasse Kombination“ (jetzt)
        </h3>
      </div>
      <div class="slide">
        <h3>
          „Unu-Ellipsoid: Wir können nicht mehr ohne!“ (Tagesspiegel)
        </h3>
      </div>
    </agile>
    <div class="logos">
      <button type="button" @click="$refs.slider.goTo(0)">
        <img src="@/assets/800px-Logo-der_spiegel.svg.png" alt="">
      </button>
      <button type="button" @click="$refs.slider.goTo(1)">
        <img src="@/assets/512px-DER_STANDARD.svg.png" alt="">
      </button>
      <button type="button" @click="$refs.slider.goTo(2)">
        <img src="@/assets/688px-JETZT_logo.svg.png" alt="">
      </button>
      <button type="button" @click="$refs.slider.goTo(3)">
        <img src="@/assets/800px-Tagesspiegel-Logo.svg.png" alt="">
      </button>
    </div>
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
  padding-top: 6rem;
  padding-bottom: 6rem;
  .logos {
    margin-top: 1rem;
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    button {
      width: calc(50% - 1rem);
      background: none;
      border: none;
    }
  }
}
</style>