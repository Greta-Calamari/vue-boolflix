<template>
<div>
<h1>Boolflix</h1>
<div class="col-10 col-md-6 col-lg-4">
        <div class="input-group">
            <input type="text" class="form-control form-control-sm " placeholder="Search Movie" aria-label="Recipient's username" aria-describedby="button-addon2" v-model="inputText">
            <button class="btn btn-outline-secondary" type="button" id="button-addon2" @click="search">Search</button>
        </div>


  </div>
</div>


    
</template>

<script>
import store from '../store.js';
export default {
    components: {  },
    name: "AppHeader",
    data(){
        return{
            inputText:"",
        } 
    },
     methods:{      
        search(){
            store.setSearch(this.inputText)
        }
    },
}
</script>

<style lang="scss">

</style>