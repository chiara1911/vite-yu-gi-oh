<template>
<section>
        <div class="row gy-4" v-if="store.cardList.length > 0">
            <div class="col-12 col-md-4 col-lg-3" >
                <CardComponent v-for="(item,index) in store.cardList"  :img="item.card_images[0].image_url" :name="item.name" :type="item.type"  />
            </div>
        </div>
    </section>
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


</style>