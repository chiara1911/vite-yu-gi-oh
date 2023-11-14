<template>
    <div class=" m-2" id="cardEl">
        <img :src="img" :alt="name">
        <div class="d-flex flex-column text-center my-auto ">
            <span class="text-uppercase text-light fw-semibold ">{{name }}</span>  
            <span >{{ type }}</span>
            
        </div>
                    

        
    </div>
</template>

<script>

import {store} from '../data/store.js';
import axios from 'axios'

export default {
     name: "CardComponent",
     props: {
       name : String,
      archetype : String,
       img : String,
    },
    components: {
        store,
        axios
    }
}
</script>

<style scoped>

#cardEl{
    background-color: #d48f38;
    width: calc( (100% / 5) - 16px);
}
</style>