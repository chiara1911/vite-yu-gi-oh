<template>
  <header>
 
  </header>

  <main>
<CardBox />

  </main>
</template>

<script>
import {store} from './data/store.js';
import axios from 'axios';
import CardBox from './components/CardBox.vue';
import CardComponent from './components/CardComponent.vue';





export default {
    name: "App",
    component: {
        CardBox,
        CardComponent
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
    components: { CardBox }
}
</script>
<style scoped></style>
