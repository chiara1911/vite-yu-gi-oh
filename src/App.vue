<template>
  <header></header>

  <main class="wrapper">
    <SearchComponent @filter-change="setParams" />
    <CardBox />
  </main>
</template>

<script>
import { store } from "./data/store.js";
import axios from "axios";
import CardComponent from "./components/CardComponent.vue";
import CardBox from "./components/CardBox.vue";
import SearchComponent from "./components/SearchComponent.vue";
export default {
  name: "App",
  components: {
    CardBox,
    CardComponent,
    SearchComponent,
  },
  data() {
    return {
      store,
    };
  },
  methods: {

    //metodo set parametri//
    setParams(search) {
      console.log(search);
      if (search) {
        this.params = {
          status: search,
        };
      } else {
        this.params = null;
      }

      this.getCharacters();
    },

    //metodo per settare i personaggi//
    getCharacters() {
      const url = store.apiUrl + store.endPoint.archetype;
      console.log('url ' + url)
      axios.get(url).then((response) => {
        store.cardList = response.data.data;
        console.log(store.cardList);
      });
    },
  },
  created() {
    this.getCharacters();
  },
};
</script>
<style scoped></style>
