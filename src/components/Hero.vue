<template>
  <section class="hero-image">
    <div class="content-container">
      <h1>unu: Ellipsoid</h1>
      <h3>Kantenlos deine Stadt entdecken!</h3>
      <button class="button white">Kaufen</button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Hero',
}
</script>

<style lang="scss" scoped>
.hero-image {
  width: 100%;
  height: calc(100vh - var(--header-height));
  background: url('../assets/hero_image_mobile.jpg');
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  @media only screen and (min-width: 600px) {
    background: url('../assets/hero_image.jpg');
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
  }
}
.content-container {
  color: white;
  height: 100%;
  width: 100%;
  padding-bottom: 4rem;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  
}
</style>