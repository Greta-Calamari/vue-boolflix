<template>
<div class="input-group mb-3 mt-5" >
  <input type="text" class="form-control" placeholder="Cerca" aria-label="" aria-describedby="button-addon2" v-model="inputText">
  <button class="btn btn-outline-secondary" type="button" id="button-addon2">Button</button>
</div>
</template>
<script>
export default {
    name:'AppSearch',
    data(){
        return{
            inputText:'',
        }
    },
}
</script>
<style lang="scss">

</style>