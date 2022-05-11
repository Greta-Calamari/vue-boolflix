<template>
<section>
    <h2 class="title">{{title}}</h2>
    <div class="row w-75 justify-content-center py-5 m-auto">
         <div class="col-12 col-sm-4 col-md-3 col-lg-2 p-0" v-for="(item) in items" :key="item.id">
              <div class="col text-center d-flex flex-column align-items-center justify-content-between">
                <div>
                   <img class="w-100 p-1" :src="'https://image.tmdb.org/t/p/original/'+ item.poster_path" alt="">
                   <h4 class="text-center fw-bold p-2 text-uppercase">{{item.title ? item.title : item.name}}</h4>   
                </div>
                <div>
                   <p class="px-2 m-0">{{item.original_title ? item.original_title :item.original_name}}</p>
                   <p class="px-2">{{item.release_date}}</p>
                   <!-- <p class="px-2">{{item.original_language}}</p>-->
                   <div>
                   <img class="flag-img" :src="require('../assets/images/' + item.original_language + '.jpg')" alt="">

                   </div>
                   <p class="px-2">{{item.vote_average}}</p>  

                </div>
              </div>
        
         </div>
     </div>

    <!-- <ul>
        <li v-for="(item) in items" :key="item.id"> -->
           
        <!-- id :{{item.id}} -->
        
        <!-- titolo originale:{{item.original_title ? item.original_title :item.original_name}}
        titolo:{{item.title ? item.title : item.name}}
        lingua:{{item.original_language}} -->
        <!-- <div v-if="!item.original_language === "></div> -->
        <!-- <img :src="require('./assets/images/' + item.original_language + '.jpg')" alt=""> -->
        <!-- voto:{{item.vote_average}} -->
<!--   
        </li>
      </ul> -->
      


</section>
    
</template>

<script>
// import state from '../store'

export default {
   name: 'GridList',
   props:['items','loader','title'],
   components:{

   },
   data(){
       return{
           

       }
   },
   methods:{
       

   },
   computed:{
       
   },
    
}
</script>
<style lang="scss">
@import "../styles/general.scss";
.title{
    color: $tt-color;
}
// .col{
//     box-shadow: 5px 10px 20px #0000006b;
    
// }

.flag-img{
    width: 20px;
}
div{
    overflow: hidden;
    color: $bg-main;
    background-color: $bg-navbar;
   
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

</style>


