<template>
  <div>
    <Header />
    <Hero />
    <section class="content-container short-info">
      <div>
        <img src="./assets/sell.svg" alt="sell">
        <p>Online bestellen ab 3.299€ oder 63€ monatlich.</p>
      </div>
      <div>
        <img src="./assets/deliver.svg" alt="deliver">
        <p>Lieferung vor die Haustür</p>
      </div>
    </section>
    <ProductColorSwitcher />
    <div class="content-container">
      <div class="slider-head">
        <h2>Für dich und deine Welt</h2>
        <p :class="{ big: over900Px() }">Dein Unu Ellipsoid schafft neue Perspektiven auf das was wirklich begeistert. Wir haben das zusammen gebracht was zusammen gehört. Ingenieurskunst aus Berlin vereint mit Design und Experience die ein wirklich allumfassendes Erlebnis schafft.</p>
      </div>
    </div>
    <Scroller v-if="over900Px()"></Scroller>
    <Slider v-if="!over900Px()"></Slider>
    <DetailsTable></DetailsTable>
    <TextSlider></TextSlider>
    <Footer></Footer>
  </div>
</template>

<script>
    /* eslint-disable vue/no-unused-components */
import Header from './components/Header.vue';
import Hero from './components/Hero.vue';
import ProductColorSwitcher from './components/ProductColorSwitcher.vue';
import Slider from './components/Slider.vue';
import DetailsTable from './components/DetailsTable.vue';
import TextSlider from './components/TextSlider.vue';
import Footer from './components/Footer.vue';
import Scroller from './components/Scroller.vue';

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    ProductColorSwitcher,
    Slider,
    DetailsTable,
    TextSlider,
    Footer,
    Scroller
},
    data() {
    return {
      innerWidth: null,
    }
  },
  methods: {
    over600Px() {
      return this.innerWidth > 600
    },
    over900Px() {
      return this.innerWidth > 900
    },
  },
  mounted() {
    this.innerWidth = window.innerWidth;
    window.addEventListener('resize', () => {
      this.innerWidth = window.innerWidth;
    })
  },
  
}
</script>

<style lang="scss">

$prime-color: #C53C2E;

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800;900&display=swap');
// Global Styles
:root {
  --header-height: 56px;
}
html {
  box-sizing: border-box;
  font-size: 16px;
}

*, *:before, *:after {
  box-sizing: inherit;
}

body, h1, h2, h3, h4, h5, h6, p, ol, ul, button {
  margin: 0;
  padding: 0;
  font-weight: 400; 
  font-family: 'Inter', sans-serif;
  // max-width: 100%;
  // overflow-x: hidden;
}

h1 {
  font-size: 3rem;
  margin-bottom: 0.5rem;
  font-weight: 500;
}
h2 {
  font-size: 3rem;
  margin-bottom: 0.5rem;
  font-weight: 500;
}
h3 {
  font-size: 2rem;
  margin-bottom: 0.6rem;
  font-weight: 500;     
}
h4 {
  font-size: 1.2rem;
  margin-bottom: 0.6rem;
}
p {
  max-width: 600px;
}
p.big {
    font-size: 1.75rem;
}
@media only screen and (min-width: 900px) {
  h1 {
    font-size: 5.1rem;
    margin-bottom: 1rem;
    font-weight: 500;
  }
  h2 {
    font-size: 5.1rem;
    margin-bottom: 0.8rem;
    font-weight: 500;
  }
  h3 {
    font-size: 2.25rem;
    margin-bottom: 0.6rem;
    font-weight: 500;
  }
  h4 {
    font-size: 1.4rem;
    margin-bottom: 0.6rem;
  }
  p.big {
    font-size: 2.5rem;
  }           
  p {
    font-size: 1.5rem;
    max-width: none;
  }           
} 
ol, ul {
  list-style: none;
}

img {
  max-width: 100%;
  height: auto;
}

.button {
  background: none;
  border: 2px solid black;
  border-radius: 64px;
  height: 40px;
  min-width: 128px;
  font-weight: 500;
  font-size: 1rem;
  max-width: 385px;
  @media only screen and (min-width: 900px) {
    height: 48px;
    font-size: 1.375rem;
  }
  &.white {
    color: white;
    border: 2px solid white;
  }
  &.solid {
    border: none;
    background: $prime-color;
    color: white;
  }
}
.content-container {
  padding: 0 2rem 0 2rem;
  max-width: 1280px;
  margin: 0 auto;
}
@media only screen and (min-width: 900px) {
  :root {
    --header-height: 80px;
  }
}

// Short Info
.short-info {
  display: flex;
  justify-content: space-around;
  column-gap: 1rem;
  padding-top: 3rem;
  padding-bottom: 3rem;
  img {
    width: 3rem;
  }
  > * {
    display: flex;
    align-items: center;
    column-gap: 1rem;
    width: 50%;
    max-width: 250px;
  }
}

.slider-head {
  margin-top: 6rem;
  @media only screen and (min-width: 900px) {
    p {
      margin-left: 12rem;
    }
  }
}
</style>
