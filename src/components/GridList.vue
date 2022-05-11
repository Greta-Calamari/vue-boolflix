<template>
<section>
    <h2>{{title}}</h2>
    <ul>
        <li v-for="(item) in items" :key="item.id">
           
        id :{{item.id}}
        titolo originale:{{item.original_title ? item.original_title :item.original_name}}
        titolo:{{item.title ? item.title : item.name}}
        lingua:{{item.original_language}}
        <!-- <div v-if="!item.original_language === "></div> -->
        <!-- <img :src="require('./assets/images/' + item.original_language + '.jpg')" alt=""> -->
        voto:{{item.vote_average}}
  
        </li>
      </ul>


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

</style>


