<template >
    <div class="wrapper">
<div class="container p-5 ">
    <h6 class="text-light bg-dark p-3 mx-2 mb-0">Found 20 elements</h6>
    <div class="row mt-0" v-if="store.cardList.length > 0">
            <div class="col-12 d-flex flex-row flex-wrap" >
                <CardComponent v-for="(item,index) in store.cardList"  :img="item.card_images[0].image_url" :name="item.name" :archetype="item.archetype"  />
            </div>
        </div>

    </div>
</div>
        
   
</template>

<script>
import {store} from '../data/store.js';
import CardComponent from './CardComponent.vue';
    export default {
        name:'CardBox',
        components : {
            CardComponent
        },
        data (){
            return{
                store
            }
        }
    }
</script>

<style lang="scss" scoped>

.container{
    background-color: white;

}
</style>