<template>
<section class="main-s">
    <h2 class="title">{{title}}</h2>
    <div class="row w-75 justify-content-center py-5 m-auto" >
         <div class="col-12 col-sm-4 col-md-3 col-lg-2 p-0" v-for="(item) in items" :key="item.id" >
            <div class=" rela col text-center d-flex flex-column align-items-center justify-content-between" @mouseover="showItem">
                
                <img class="w-100 p-1" :src="'https://image.tmdb.org/t/p/w342/'+ item.poster_path" alt="">
                <div class="showCard" :class="show ? 'active'  : ''">
                   <h4 class="text-center fw-bold p-2 text-uppercase">{{item.title ? item.title : item.name}}</h4>   
                   <p class="px-2 m-0">{{item.original_title ? item.original_title :item.original_name}}</p>
                   <p class="px-2">{{item.release_date}}</p>
                   <div v-if="item.original_language === 'en' || item.original_language === 'it' ">
                        <img class="flag-img" :src="require('../assets/images/' + item.original_language + '.jpg')" alt="">
                   </div>
                   <div v-else>
                       <img class="flag-img" :src="require('../assets/images/' + 'world.jpg')" alt="">
                   </div>
                   <p class="px-2 star">
                   <i v-for="index in halfNumber(item.vote_average)" :key="index" class="fa-regular fa-star"></i>
                    </p>  

            </div>
        </div>
        
    </div>
</div>
<!-- :class="show ? 'active' : '' " -->
                   
                
                   

                
                


                   
                   
            

                   
                


</section>
    
</template>

<script>
// import state from '../store'
import "../styles/general.scss";

export default {
   name: 'GridList',
   props:['items','loader','title'],
   components:{

   },
   data(){
       return{
           show: false,
           

       }
   },
   methods:{
       
        halfNumber(number){
            return Math.round(number/2)
        },
        showItem(){
         return this.show = true 
    },

   },
   computed:{
       
   },
    
}
</script>
<style lang="scss">
@import "../styles/general.scss";

.rela{
    position: relative;
}

.star{
    color: yellow;
}

.title{
    color: $tt-color;
}


.main-s{
    
  background-color: $bg-navbar;
}

.flag-img{
    width: 50px;
}
div{
    overflow: hidden;
    color: $bg-main;
    
   
}
h4{
    color: antiquewhite;
    font-size: 20px;
    text-overflow: ellipsis;
}
p{
    color: rgb(255, 255, 255);
    font-size: 20px;
}

.active{
  display: block;
}

.showCard{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 300px;
    display: none;
    padding: 20px 10px;
    overflow-y: auto;
}
    
    





</style>


