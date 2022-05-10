<template>
<div>

    <div class="card text-center d-flex flex-column align-items-center justify-content-between">
    <div>
     <img class="w-100 p-1" :src="'https://image.tmdb.org/t/p/original/'+ item.poster_path" alt="">
    <h4 class="text-center fw-bold p-2 text-uppercase">{{item.title}}</h4>   
    </div>
    <div>
        <p class="px-2 m-0">{{item.original_title}}</p>
        <p class="px-2">{{item.release_date}}</p>    
        <p class="px-2">{{item.vote_average}}</p>  
    </div>
</div>

</div>
    
</template>

<script>
export default {
    name:'AppCard',
    props:{
        item:Object,
    }
    

    
}
</script>

<style lang="scss">
@import "../style/general.scss";


.col{
    box-shadow: 5px 10px 20px #0000006b;
}

h4{
    color: antiquewhite;
    font-size: 20px;
    text-overflow: ellipsis;
}
p{
    color:black;
    font-size: 20px;
}

</style>