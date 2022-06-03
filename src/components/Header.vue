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
        <button class="buy solid">Kaufen</button> 
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
  background: rgb(247, 243, 240) none repeat scroll 0% 0%;
  .content-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 56px;
  }
  img {
    width: 56px;
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
