<template>
    <div class="card bg-transparent border-0 ">
        <img :src="img" class="card-img-top" :alt="name">
        <div class="card-body text-center">
            <h5 class="card-title">{{ archetype }}</h5>
            <h6 class="card-title">{{ name }}</h6>
            

        </div>
    </div>
</template>

<script>
export default {

    name: 'CardComponent',
    props: {
       name : String,
       archetype : String,
       img : String,
    },
}
</script>

<style scoped>

</style>