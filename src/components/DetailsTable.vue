<template>
  <section>
    <div class="content-container">
      <h2>Technische Details</h2>
      <div class="container">
        <!-- <div class="row"> -->
          <div class="item">
            <h3>Batterie</h3>
            <p>8-12 Wochen (je nach Nutzung) oder maximal 120km</p>
          </div>
          <div class="item">
            <h3>Stauraum</h3>
            <p>Bruttostauraum: 300 l</p>
            <p>z. B. 4 große Koffer</p>
            <p>oder ein Fahrrad</p>
          </div>
          <div class="item">
            <h3>Passagiere</h3>
            <p>Gemacht für dich und deine Freunde.</p>
            <p>Je nach Gepäck können 1-3 Freunde mitfahren.</p>
          </div>
        <!-- </div> -->
        <!-- <div class="row"> -->
          <div class="item">
            <h3>Geschwindigkeit</h3>
            <p>45 km/h</p>
            <p>Erreichst du in 3 Sekunden.</p>
          </div>
          <div class="item">
            <h3>Unser Versprechen</h3>
            <p>Wenn du Unzufrieden bist kannst du den UNU innerhalb von 4 Wochen einfach zurück geben. </p>
          </div>
          <div class="item">
            <h3>Garantie</h3>
            <p>Du erhältst 2 Jahre Garantie, wir übernehmen alle Reparaturkosten. (ausgenommen sind Verschleißteile)</p>
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