<template>
  <div id="app">
    <header>
    <h1 class="display-6">Boolflix</h1>
    
    <search-bar @performSearch="search"/>
    </header>
  

    <main>
      
      
      <grid-list :items="movies" title="Movies" :loader="loading"/>
      <grid-list :items="series" title="Series" :loader="loadingSeries"/>

    </main>

  
  </div>
</template>

<script>
import axios from 'axios'
import GridList from './components/GridList.vue'
import SearchBar from './components/SearchBar.vue'


export default {
  name: 'App',
  components: {
    SearchBar,
    GridList,
  },data(){
    return{
      apiKey:'7bb93464ea396b5c4394f00e6170ccea',
      apiPath:'https://api.themoviedb.org/3/search/',
      movies:[],
      series:[],
      loading:false,
      loadingSeries:false,
      

    }
  },

    
  methods:{
    getMovies(queryParams){
      
      axios.get(this.apiPath + 'movie',queryParams).then((res)=>{
        // console.log(res.data.results)
        this.movies = res.data.results;
        this.loading = false;


      }).catch((error)=>{
        console.log(error)
      })
    },getSeries(queryParams){
      axios.get(this.apiPath + 'tv',queryParams).then((res)=>{
        // console.log(res.data.results)
        this.series = res.data.results;
        this.loadingSeries = false;


      }).catch((error)=>{
        console.log(error)
      })

    },
    search(text){
      const queryParams = {
        params:{
          api_key:this.apiKey,
          query:text,

        }
      }
      this.loading = true;
      this.loadingSeries = true;
      this.getMovies(queryParams)
      this.getSeries(queryParams)

    },
  }
  
}
</script>

<style lang="scss">
@import './styles/general.scss';


h1{
  color: $tt-color;
}

</style>
