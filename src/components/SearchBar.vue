<template>
  <div>
   <div class="input-group my-3">
            <input type="text" class="form-control" placeholder="Cerca Per Titolo" v-model="inputText" @keyup.enter="$emit('performSearch',inputText)" aria-label="Recipient's username" aria-describedby="button-addon2">
            <button @click="cerca" class="btn btn-outline-secondary" type="button" id="button-addon2">Cerca</button>
    </div>
  </div>
</template>
<script>
// import state from '../store'
export default {
  name:'SearchBar',
  data(){
    return{
      inputText:'',
      

    }
  },
  methods:{
    cerca(){
      this.$emit('performSearch',this.inputText)
      this.inputText = ''
    }

  },computed:{
    
  },
  
}
</script>
<style lang="scss">


</style>