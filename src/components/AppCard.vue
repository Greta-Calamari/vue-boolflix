<template>
<div>

    <div class="card">
        <div>{{item.original_title}}</div>
        <div>{{item.title}}</div>
        <div>{{item.original_language}}</div>
        <div>{{item.vote_average}}</div>
        
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
.card{
    height: 300px;
    background: black;
    color: black;
}

</style>