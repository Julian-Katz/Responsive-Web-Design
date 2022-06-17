<template>
  <section ref="section">
    <div class="content-container">
      <div ref="text1" class="text-item">
        <h3>Atemberaubende Beschleunigung</h3>
        <p>Im null Komma nichts erreichst du deine Geschwindigkeit. Nie mehr  warten auf das was kommt.</p>
      </div>
      <div ref="text2" class="text-item">
        <h3>Völlig Kantenloses Erlebnis</h3>
        <p>Keine Kanten, nichts was dich aufhält. Ein Erlebnis ohne Nachteile, nichts stoppt dich. </p>
      </div>
    </div>
    <div class="img-container " ref="img1">
      <img class="img1" src="@/assets/UNU_NIGHT.jpg" alt="">
    </div>
    <div class="img-container second" ref="img2">
      <img class="img2" src="@/assets/UNU_DAY.jpg" alt="">
    </div>
    <div class="background" ref="background"></div>
  </section>
</template>

<script>
  /* eslint-disable no-unused-vars */
export default {
  name: 'Scroller',
  setup() {


  },
  mounted() {
    const options = {
      // root: this.$refs.section,
      rootMargin: '0px',
      threshold: [0.5, 0.9]
    }
    let observer = new IntersectionObserver( (entries) => {
      entries.forEach( entry => {
        // console.log(entry);
        // if (entry.isIntersecting && entry.boundingClientRect.y > 0) {
        //   console.log('case start down');
        //   this.$refs.img1.classList.add("img-fixed")
        //   this.$refs.img2.classList.add("img-fixed")
          // document.addEventListener('scroll', (e) => {
          //   console.log(e);
          // })
        // }
        if (!entry.isIntersecting && entry.boundingClientRect.y > 0 && entry.time > 3000) {
          console.log('case start up');
          this.$refs.img1.classList.remove("img-fixed")
          this.$refs.img2.classList.remove("img-fixed")
          this.$refs.img2.firstChild.style = `clip-path: polygon(0 0%, 100% 0%, 100% 100%, 0% 100%);`;
        }

        if (!entry.isIntersecting && entry.boundingClientRect.y < 0) {
          console.log('case end down');
          this.$refs.img1.classList.remove("img-fixed")
          this.$refs.img2.classList.remove("img-fixed")
          this.$refs.img1.classList.add("img-absolute-end")
          this.$refs.img2.classList.add("img-absolute-end")
          this.$refs.img2.firstChild.style = `clip-path: polygon(0 100%, 100% 100%, 100% 100%, 0% 100%);`;
        }
        if(entry.isIntersecting && entry.boundingClientRect.y < 0) {
          console.log('case end up');
          this.$refs.img1.classList.add("img-fixed")
          this.$refs.img2.classList.add("img-fixed")
          this.$refs.img1.classList.remove("img-absolute-end")
          this.$refs.img2.classList.remove("img-absolute-end")
          document.addEventListener('scroll', () => {
              let distance = this.$refs.text1.getBoundingClientRect().top - this.$refs.text2.getBoundingClientRect().top;
            if (this.$refs.background.getBoundingClientRect().top < 0 && this.$refs.background.getBoundingClientRect().top > distance) {
              let scrollPercentage = this.$refs.background.getBoundingClientRect().top / distance * 100;
              scrollPercentage = scrollPercentage.toFixed(2);
              this.$refs.img2.firstChild.style = `clip-path: polygon(0 ${scrollPercentage}%, 100% ${scrollPercentage}%, 100% 100%, 0% 100%);`;
            }
          })
        }
      })
    }, options);

    observer.observe(this.$refs.background);

  },
  methods: {
    // handleStartDown(e) {
    //   console.log(e);
    // }
  }
}
</script>

<style lang="scss" scoped>
section {
  // height: calc(200vh - var(--header-height) * 2);
  height: 200vh;
  position: relative;
  // padding: 6rem 0;
  // margin: 6rem 0;
  margin-top: 6rem;
  .content-container {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    height: 100%;
  }
  .img-container {
    width: 35vw;
    max-width: 600px;
    aspect-ratio: 16 / 9;
    position: absolute;
    top: 25%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    align-items: flex-end;
    &.img-absolute-end {
      top: 75%;
    }
    &.img-fixed {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    img {
      height: 100%;
      width: 100%;
      object-fit: cover;
      object-position: bottom;
    }
    // .img2 {
    //   clip-path: polygon(0 50%, 100% 50%, 100% 100%, 0% 100%);
    // }
  


  }
  .text-item {
    max-width: 300px;
  }
  .background {
    position: absolute;
    top: 0;
    right: 0;
    width: 50vw;
    height: 100%;
    background: #C53C2E;
    z-index: -5;
  }
}
</style>