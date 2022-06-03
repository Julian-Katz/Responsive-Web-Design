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
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Hero from './components/Hero.vue';
import ProductColorSwitcher from './components/ProductColorSwitcher.vue';

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    ProductColorSwitcher,
  }
}
</script>

<style lang="scss">

$prime-color: #C53C2E;

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800;900&display=swap');
// Global Styles
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
}

h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  font-weight: 400;
}
h2 {
  font-size: 3rem;
  margin-bottom: 0.8rem;
}
h3 {
  font-size: 2rem;
  margin-bottom: 0.6rem;
}
h4 {
  font-size: 1.2rem;
  margin-bottom: 0.6rem;
}

ol, ul {
  list-style: none;
}

img {
  max-width: 100%;
  height: auto;
}

button {
  background: none;
  border: 2px solid black;
  border-radius: 64px;
  height: 40px;
  min-width: 128px;
  font-weight: 400;
  font-size: 1rem;
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
  padding: 0 1.5rem 0 1.5rem;
  max-width: 1280px;
  margin: 0 auto;
}

// Short Info
.short-info {
  display: flex;
  column-gap: 1rem;
  padding-top: 3rem;
  padding-bottom: 3rem;
  > * {
    width: 50%;
  }
}
</style>
