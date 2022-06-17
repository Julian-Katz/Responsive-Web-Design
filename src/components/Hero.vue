<template>
  <section class="hero-image">
    <video src="@/assets/Hero_video_cut.mp4" autoplay muted loop></video>
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
  position: relative;
  overflow: hidden;
  margin-top: var(--header-height);
  video {
    height: 100%;
    width: 100%;
    position: absolute;
    object-fit: cover;
    top: 0;
    z-index: -5;
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