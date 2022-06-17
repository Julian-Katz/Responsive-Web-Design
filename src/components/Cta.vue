<template>
  <section class="content-container">
    <h2>Einfach Zuschlagen</h2>
    <button class="button solid">Kaufen</button>
    <p class="big">oder weitere Informationen erhalten</p>
    <form action="#">
      <!-- <label for="e-mail">Email</label> -->
      <input type="e-mail" name="e-mail" placeholder="E-Mail">
      <button class="button black" type="submit">Abschicken</button>
    </form>
  </section>
</template>

<script>

export default {
  name: 'ProductColorSwitcher',
  data() {
    return {
    }
  },
}
</script>

<style lang="scss" scoped>
section {
  padding-top: 6rem;
  // padding-bottom: 6rem;
  width: 100%;
  display: flex;
  flex-direction: column;
  button {
    margin-bottom: 2rem;
  }
  form {
    margin: 1rem 0;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    row-gap: 1rem;
    column-gap: 1rem;
    button {
      margin-bottom: 0;
      width: 100%;
    }
  }
  input {
    font-size: 1rem;
    font-weight: 500;
    font-family: 'Inter', sans-serif;
    width: 100%;
    border: 2px solid black;
    border-radius: 64px;
    padding: 1rem 2rem;
    max-width: 385px;
    max-height: 48px;
  }
}
</style>
