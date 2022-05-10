<template>
<div>

    <div class="card">
        <div>{{item.title}}</div>
        <div>{{item.name}}</div>
        <div>{{item.language}}</div>
        <div>{{item.vote}}</div>
        
    </div>


</div>
    
</template>

<script>
export default {
    name:'AppCard',
    props:{
        item:Object
    }
    

    
}
</script>

<style lang="scss">
.card{
    height: 300px;
    color: black;
}

</style>