<template>
<div>

   <div class="row w-75 justify-content-center py-5 m-auto">
        <div class="col-12 col-sm-4 col-md-3 col-lg-2 p-0"
        v-for="(album, index) in searchedMovies" :key="index">
        <app-card :item="album"/>
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
             
            
            lastPopular:[],
            api:'https://api.themoviedb.org/3/search/movie?api_key=6853d87823c5e52e6b967b2482fca241&language=it-IT&query=',
            apiKey:'api_key=7bb93464ea396b5c4394f00e6170ccea',
            apiSearch:'&language=it-IT&query=',
            // apiLastPopular:'https://api.themoviedb.org/3/movie/popular?api_key=6853d87823c5e52e6b967b2482fca241&language=it-IT&page=1',
            searchedMovies:[],
            authors:[],
            searchText:"",

        }


    },methods:{
        mySearch(text){
              
          
              axios.get(this.api + store.state.search).then((res)=>{
              this.searchedMovies = res.data.results;
              console.log(this.albumList)
              console.log(this.authors)
          }).catch((error) => {
              console.log(error)
          })
                 this.searchText = text; 
                 
          },
          
          myfind(){
              console.log(store.state.search)
              return store.state.searchText
          }

    }
        
    
    

  
        

    

}
</script>

<style lang="scss">


</style>