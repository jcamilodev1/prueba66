<template>
  <div class="home">
    <picture class="home__logo">
      <img src="../assets/img/pokemon.svg" alt="Pokemon" title="Pokemon">
    </picture>
    <h1>Welcome to Pokédex</h1>
    <p>The digital encyclopedia created by Professor Oak is an invaluable tool to Trainers in the Pokémon world.</p>
    <btn url="/seacher" text="Get started"></btn>
  </div>
</template>

<script>
import Btn from '../components/Btn.vue'
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    Btn
}
}
</script>
<style lang="scss">
  .home{
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    font-family: var(--font);
    h1{
      font-size: 2.6rem;
      font-weight: 700;
      margin-bottom: 30px;
      color: var(--colorTile);
      font-family: var(--font);
    }
    p{
        font-family: var(--font);
      font-size: 1.8rem;
      margin-bottom: 50px;
      color: var(--colorText);
    }
  }

</style>
