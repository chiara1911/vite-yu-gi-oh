<template>
<section>
        <div class="row gy-4" v-if="store.cardList.length > 0">
            <div class="col-12 col-md-4 col-lg-3" v-for="(item, index) in store.cardList" :key="item.id">
                <CardComponent :image="item.img" :name="item.name" :archetype="item.archetype"  />
            </div>
        </div>
    </section>
</template>

<script>
import {store} from '../data/store.js';
import cardComponent from './CardComponent.vue';
    export default {
        name:'CardList',
        components : {
            cardComponent
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