<template>
  <section>
    <section class="container">
      <loader v-if="statusChange"></loader>
      <article class="container__seacher">
        <search></search>
        <article class="container__seacher-txt" v-if="error">
          <h2>Uh-oh!</h2>
          <p>You look lost on your journey!</p>
          <btn url="/" text="Go back home"></btn>
        </article>
        <card-list></card-list>
        <!-- <btn :url='"/seacher/" + (parseInt($route.params.username) + 1) ' text="Go back home"></btn>
        <btn :url='"/seacher/" + (parseInt($route.params.username) + 1) ' text="Go back home"></btn>

        <h1>{{ $route.params }}</h1>
        <h1>{{ $route.params }}</h1> -->

      </article>
    </section>
    <nav-bar></nav-bar>
  </section>
</template>

<script>
import Btn from "../components/Btn.vue";
import CardList from "../components/CardList.vue";
import Loader from "../components/Loader.vue";
import Search from "../components/Search.vue";
import NavBar from "../components/NavBar.vue";
import { computed, ref } from "vue";
import { useStore } from "vuex";

export default {
  components: { Loader, Search, Btn, CardList, NavBar },
  name: "Seacher",
  setup() {
    const store = useStore();
    const statusChange = computed(() => {
      return store.state.loader;
    });
    const error = computed(() => {
      return store.state.error;
    });
    return { statusChange, error };
  },
};
</script>

<style lang="scss">
.container {
  max-width: 900px;
  margin: 0 auto;
  padding: 20px;
  &__seacher {
    &-txt {
      h2 {
        font-family: var(--font);
        font-size: 3.6rem;
        font-weight: 700;
        margin: 30px 0;
        color: var(--colorTitle);
      }
      p {
        font-family: var(--font);
        font-size: 1.8rem;
        margin-bottom: 50px;
        color: var(--colorText);
      }
    }
  }
}
</style>