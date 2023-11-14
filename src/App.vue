<template>
  <header>
 
  </header>

  <main class="wrapper">

<SearchComponent />
<CardBox />

  </main>
</template>

<script>
import {store} from './data/store.js';
import axios from 'axios';
import CardComponent from './components/CardComponent.vue';
import CardBox from './components/cardbox.vue';
import SearchComponent from './components/SearchComponent.vue';
export default {
    name: "App",
    components: {
        CardBox,
        CardComponent,
        SearchComponent,
        
    },
    data() {
        return {
            store
        };
    },
    methods: {
        getCharacters() {
            const url = store.apiUrl;
            axios.get(url).then((response) => {
                store.cardList = response.data.data;
                console.log(store.cardList);
            });
        }
    },
    created() {
        this.getCharacters();
    },
 
}
</script>
<style scoped></style>
