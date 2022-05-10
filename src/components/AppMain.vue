<template>
<div>

    <div class="row">
        <div class="col-6 col-md-4 col-lg-3" v-for="movie in tList" :key="movie.id">
            <AppCard :item="movie"/>

        </div>
        
        
    </div>


</div>
    
</template>

<script>
import AppCard from './AppCard.vue'
import axios from 'axios';

export default {
    name:'AppCard',
    components:{
        AppCard,
    },

    
    data(){
        return {
             apiUrl:'https://api.themoviedb.org/3/serach/',
             apiKey:'7bb93464ea396b5c4394f00e6170ccea',
             tList:[],
             movies:[],

        }


    },
    created(){
        axios.get(this.apiUrl +'movie').then((res)=>{
            console.log(this.tList)
            this.tList = res.data
            this.tList.forEach((el)=>{
                if(!this.movies.includes(el.movies)){
                    this.movies.push(el.movies)
                }
            });

        }).catch((error)=>{
            console.log(error)
            
        })

  }
}
</script>

<style lang="scss">

</style>