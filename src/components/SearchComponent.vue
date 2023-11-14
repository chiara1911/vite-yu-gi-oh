<template>
    <select name="search-component" id="search-component" v-model="typeSelect" @change="passData">
        <option value="tutti" >tutti</option>
        <option value="alien" >alien</option>
        <option value="alien2" >alien2</option>
        <option value="alien3" >alien3</option>
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
                console.log('pass ' + this.passData)
            }
           
        }
       
        
    }
</script>

<style lang="scss" scoped>

</style>