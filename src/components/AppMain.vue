<template>
<div>

   <div class="row w-75 justify-content-center py-5 m-auto">
        <div class="col-12 col-sm-4 col-md-3 col-lg-2 p-0"
        v-for="(items, index) in searchedMovies" :key="index">
        <AppCard :item="items"/>
        <button @click="mySearch" >cerca</button>
        </div>
    </div>


</div>
    
</template>

<script>
import store from '../store.js';
import axios from 'axios';
import AppCard from './AppCard.vue'

export default {
    name:'AppCard',
    components:{
        AppCard,
    },

    
    data(){
        return {
             
            
            
            api:'https://api.themoviedb.org/3/search/movie?api_key=6853d87823c5e52e6b967b2482fca241&language=it-IT&query=',
            apiKey:'api_key=7bb93464ea396b5c4394f00e6170ccea',
            apiSearch:'&language=it-IT&query=',
            searchedMovies:[],
            authors:[],
            searchText:"",

        }


    },mounted(){
        axios.get(this.api + store.state.search).then((res)=>{
            this.searchedMovies = res.data.results;
            console.log(this.authors)
        }).catch((error) => {
            console.log(error)
        })
    }
        
    
    

  
        

    

}
</script>

<style lang="scss">


</style>