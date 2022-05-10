<template>
<div>

    <div class="row">
        <div class="col-6 col-md-4 col-lg-3" v-for="(movies,index) in tList" :key="index">
            <AppCard :item="movies"/>

        </div>
        
        
    </div>


</div>
    
</template>

<script>
import axios from 'axios';
import AppCard from './AppCard.vue'

export default {
    name:'AppCard',
    components:{
        AppCard,
    },

    
    data(){
        return {
             apiUrl:'https://api.themoviedb.org/3/search/',
             apiKey:'api_key=7bb93464ea396b5c4394f00e6170ccea',
             tList:[],
             movies:[],

        }


    },
    mounted(){
        axios.get(this.apiUrl +'movie?'+ this.apiKey +'&query=star+wars+empire').then((res)=>{
            console.log(res.data.response)
            this.tList = res.data.response
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