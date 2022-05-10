<template>
  <div class="input-group mb-3">
    <select name="species" id="species" v-model="inputText" @change="changeSearch">
        <option value="">all</option>
        <option :value="specie" v-for="(specie,index) in characterSpecies" :key="index">{{specie}}</option>
    </select>
    <div class="input-group-append">
        <button class="btn btn-outline-secondary" type="button" @click="changeSearch">Search</button>
        <button class="btn btn-outline-secondary" type="button" @click="reset">Reset</button>
    </div>
</div>
</template>

<script>
export default {
    name:'SearchBar',
    data(){
        return{
            inputText:'',
        }
    },
    props:['characterSpecies'],

    methods:{
        changeSearch(){
            this.$emit('performSearch', this.inputText);
            this.inputText=''
        },
        reset(){
            this.inputText =''
            this.$emit('search', this.inputText)
        }
    }
}
</script>

<style lang="scss">

</style>