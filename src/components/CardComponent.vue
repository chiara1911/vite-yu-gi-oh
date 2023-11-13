<template>
    <div class="card bg-transparent border-0 ">
        <img :src="img" :alt="name" class="card-img">
        
            <h5>{{ type }}</h5>
            <h6>{{name }}</h6>
            

        
    </div>
</template>

<script>

import {store} from '../data/store.js';
import axios from 'axios'

export default {
     name: "CardComponent",
     props: {
       name : String,
      type : String,
       img : String,
    },
    components: {
        store,
        axios
    }
}
</script>

<style scoped>

.card-img{
    display: block;
    width: 200px;
    height: 200px;
}
</style>