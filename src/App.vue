<template>
  <header>
    <h1>ciao</h1>
  </header>

  <main class="container"></main>
</template>

<script>
import { store } from "./data/store.js";
import axios from "axios";
import cardList from "./components/CardList.vue";
import cardComponent from "./components/CardComponent.vue";

export default {
  name: "App",
  components: {
    cardList
  },
  data(){
    return{
      store
    }
  },
  methods: {
    getCharacters() {
      const url = store.apiUrl;
      axios.get(url).then((response) => {
        console.log(cardComponent)
        store.cardList = response.data.data;
      })
    }

  },

created() {
    this.getCharacters();
}
}
</script>
<style scoped></style>
