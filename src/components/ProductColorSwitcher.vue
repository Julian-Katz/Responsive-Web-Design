<template>
  <section class="content-container">
    <h2>Farben, die zu dir passen</h2>
    <div class="switcher-container">
      <div class="images">
        <img class="black" v-show="showImage === 'black'" src="../assets/product_black.png" alt="">
        <img v-show="showImage === 'blue'" src="../assets/product_blue.png" alt="">
        <img v-show="showImage === 'green'" src="../assets/product_green.png" alt="">
        <img v-show="showImage === 'grey'" src="../assets/product_grey.png" alt="">
        <img v-show="showImage === 'red'" src="../assets/product_red.png" alt="">
      </div>
      <div class="pagination">
        <button @click="showImage = 'black'" class="black"></button>
        <button @click="showImage = 'blue'" class="blue"></button>
        <button @click="showImage = 'green'" class="green"></button>
        <button @click="showImage = 'grey'" class="grey"></button>
        <button @click="showImage = 'red'" class="red"></button>
      </div>
    </div>
  </section>
</template>

<script>

export default {
  name: 'ProductColorSwitcher',
  data() {
    return {
      showImage: 'black',
    }
  },
}
</script>

<style lang="scss" scoped>
section {
  @media only screen and (min-width: 600px) {
    min-height: calc(100vh - 56px);
  }
  min-height: calc(600px);
  padding-top: 6rem;
  background: lightgrey;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  position: relative;
  h2{
    color: white;
    padding-bottom: 3rem;
    margin-bottom: 0;
  }
  .switcher-container {
    max-width: 900px;
    margin: 0 auto;
    .pagination {
      position: absolute;
      bottom: 6rem;
      left: 50%;
      transform: translateX(-50%);
      width: 80%;
      max-width: 385px;
      border: 2px solid black;
      border-radius: 30px;
      padding: 0.5rem;
      display: flex;
      justify-content: space-around;
      align-items: center;
      z-index: 10;
      button {
        border: none;
        border-radius: 100%;
        height: 1.5rem;
        aspect-ratio: 1;
        &.black {
          background: black;
        }
        &.blue {
          background: blue;
        }
        &.green {
          background: green;
        }
        &.grey {
          background: grey;
        }
        &.red {
          background: red;
        }
      }
    }
  }

}
</style>
