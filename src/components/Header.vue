<template>
  <header>
    <div class="content-container">
      <div class="left">
        <img class="logo" src="../assets/logo.svg" alt="">
        <!-- <nav>
          <ul>
            <li>Scooter</li> 
            <li>Help Center</li>
            <li>Business</li>
            <li>Batterie-Abo</li>
          </ul>
        </nav> -->
      </div>
      <div class="right">
        <button class="button solid">Kaufen</button> 
        <!-- <img class="bars" src="../assets/bars.svg" alt=""> -->
      </div>
    </div>
  </header>
</template>

<script>

export default {
  name: 'Header',
}
</script>

<style lang="scss" scoped>
// Header Styles
header {
  background: rgb(255, 255, 255) none repeat scroll 0% 0%;
  position: fixed;
  top: 0;
  width: 100vw;
  z-index: 100;
  .content-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: var(--header-height);
  }
  img {
    width: var(--header-height);
  }
  .bars {
    border: none;
    min-width: none;
    transform: translateY(25%);
    margin-left: 1rem;
    height: 14px;
    width: 32px;
  }
}
</style>
