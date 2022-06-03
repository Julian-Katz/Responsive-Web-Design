<template>
  <section class="hero-image">
    <div class="content-container">
      <h1>unu: Ellipsoid</h1>
      <h4>Kantenlos deine Stadt entdecken!</h4>
      <button class="white">Kaufen</button>
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
  width: 100vw;
  height: calc(100vh - 56px);
  background: url('../assets/hero_image_mobile.jpg');
  background-position: center;
  background-size: cover;
  background-repeat: none;
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