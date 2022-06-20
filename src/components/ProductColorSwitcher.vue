<template>
<div class="background">
  <section class="content-container">
    <h2>Farben, die zu dir passen</h2>
    <div class="switcher-container">
      <div class="images">
        <TransitionGroup name="list">
          <img v-show="showImage === 'red'" src="../assets/product_red.png" alt="" key="red">
          <img v-show="showImage === 'blue'" src="../assets/product_blue.png" alt="" key="blue">
          <img v-show="showImage === 'green'" src="../assets/product_green.png" alt="" key="green">
          <img v-show="showImage === 'grey'" src="../assets/product_grey.png" alt="" key="grey">
          <img v-show="showImage === 'black'" src="../assets/product_black.png" alt="" key="black">
        </TransitionGroup>
        <img class="shadow" src="@/assets/switcher_shadow.png" alt="">
      </div>
      <div class="pagination">
        <button @click="showImage = 'red'" class="red"></button>
        <button @click="showImage = 'blue'" class="blue"></button>
        <button @click="showImage = 'green'" class="green"></button>
        <button @click="showImage = 'grey'" class="grey"></button>
        <button @click="showImage = 'black'" class="black"></button>
      </div>
    </div>
  </section>
</div>
</template>

<script>

export default {
  name: 'ProductColorSwitcher',
  data() {
    return {
      showImage: 'red',
    }
  },
}
</script>

<style lang="scss" scoped>
.background {
  background: rgb(255,255,255);
  background: radial-gradient(circle, rgba(255,255,255,1) 0%, rgba(20,20,20,1) 100%);
  background: radial-gradient(circle at 45% 50%, rgba(255, 255, 255, 1) 0%, rgba(20, 20, 20, 1) 100%);
  z-index: 1;
}
section {
  @media only screen and (min-width: 600px) {
    padding-bottom: 10rem;

  }
  // min-height: calc(600px);
  height: 100%;
  padding-top: 6rem;
  padding-bottom: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  position: relative;
  overflow: hidden;
  h2{
    color: white;
    padding-bottom: 3rem;
    margin-bottom: 0;
  }
  .switcher-container {
    max-width: 600px;
    margin: 0 auto;
    height: 40vh;
    width: 100%;
    .images {
      position: relative;
      width: 100%;
      height: 40vh;
      .shadow {
        position: absolute;
        bottom: -35%;
        left: -5%;
        transform: scale(200%);
        z-index: 0;
      }

      img {
        position: absolute;
        width: 100%;
        z-index: 5;
      }
    }
    .pagination {
      position: absolute;
      bottom: 4rem;
      left: 50%;
      transform: translateX(-50%);
      width: 80%;
      max-width: 385px;
      // border: 2px solid white;<
      border-radius: 30px;
      padding: 0.5rem;
      display: flex;
      justify-content: space-around;
      align-items: center;
      z-index: 10;
      background: white;
      button {
        border: none;
        border-radius: 100%;
        height: 1.5rem;
        aspect-ratio: 1;
        cursor: pointer;
        &.black {
          background: #141414;
        }
        &.blue {
          background: #283751;
        }
        &.green {
          background: #275444;
        }
        &.grey {
          background: #D0D2CE;
        }
        &.red {
          background: #C53C2E;
        }
      }
    }
  }
  @media only screen and (min-width: 1921px) {
    .switcher-container {
      max-width: 800px;
    }
  }

}
.list-enter-active {
  z-index: 5;
}
.list-enter-active,
.list-leave-active {
  transition: all 0.8s ease-in-out;
}
// .list-leave-from {

// }
// .list-leave-to {

// }
.list-enter-from{
  clip-path: polygon(0 0, 0 0, 0 100%, 0% 100%);
}
.list-enter-to {
  clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
}

</style>
