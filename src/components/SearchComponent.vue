<template>
    <select name="search-component" id="search-component" v-model="typeSelect" @change="passData">
        <option value="" >tutti</option>
        <option value="alien" >alien</option>
        <option value="Melodious" >Melodious</option>
        <option value="Noble Knight" >Noble Knight</option>
    </select>
</template>

<script>

    export default {
        name: 'SearchComponent',
        data(){
            return {
                typeSelect:''
            }
        },
        methods: {

            passData(){
                this.$emit('filterChange', this.typeSelect);
               
            }
           
        }
       
        
    }
</script>

<style lang="scss" scoped>

</style>