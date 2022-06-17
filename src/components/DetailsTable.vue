<template>
  <section>
    <div class="content-container">
      <h2>Technische Details</h2>
      <div class="container">
        <!-- <div class="row"> -->
          <div class="item">
            <h3>Batterie</h3>
            <p>8-12 Wochen (je nach Nutzung)</p>
          </div>
          <div class="item">
            <h3>Stauraum</h3>
            <p>Bruttostauraum: 45 l</p>
            <p>2 Batterien + 33 l.</p>
            <p>42 x 32 x 35 cm</p>
          </div>
          <div class="item">
            <h3>Passagiere</h3>
            <p>Gemacht für dich und deine Freunde.</p>
            <p>2 Batterien + 33 l.</p>
            <p>42 x 32 x 35 cm</p>
          </div>
        <!-- </div> -->
        <!-- <div class="row"> -->
          <div class="item">
            <h3>Geschwindigkeit</h3>
            <p>45 km/h</p>
          </div>
          <div class="item">
            <h3>Akku</h3>
            <p>1.78 kWh Lithium Ion (LG)</p>
            <p>Tragbar, 10,5 kg</p>
            <p>Haltbarkeit 7-10 Jahre / 1.000</p>
            <p>Ladezyklen</p>
            <p>Gehäuse: schwarz, gebürstetes Aluminim</p>
          </div>
          <div class="item">
            <h3>Aufladen</h3>
            <p>220V Ladegerät</p>
            <p>Passiv gekühlt (lautlos)</p>
            <p>Ladezeit maximal 7 Std</p>
          </div>
        <!-- </div> -->
      </div>
    </div>
  </section>
</template>

<script>


  export default {

  };
</script>

<style lang="scss" scoped>
section {
  background: #1C1C1C;
  color: white;
  padding-bottom: 6rem;
  padding-top: 6rem;
  .item {
    margin-bottom: 2rem;
    p {
      color: #D0D2CE;
    }
  }
  @media only screen and (min-width: 600px) {
    .container {
      display: flex;
      flex-wrap: wrap;
      column-gap: 2rem;
    }
    .item {
      height: 120px;
      width: calc(50% - 2rem);
      overflow: hidden;
    }
  }
  @media only screen and (min-width: 900px) {
    .item {
      height: 200px;
    }
  }
  @media only screen and (min-width: 1280px) {
    .item {
      width: calc(33% - (2rem * 2));
    }
  }
}

</style>