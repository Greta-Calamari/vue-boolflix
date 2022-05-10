<template>
<div>

    <div class="row">
        <div class="col-6 col-md-4 col-lg-3">
            <AppCard/>

        </div>
        
        
    </div>


</div>
    
</template>

<script>
import AppCard from './AppCard.vue'
export default {
    name:'AppCard',
    components:{
        AppCard,
    },
    data(){
        return {
             apiUrl:'https://api.themoviedb.org/3/serach/',
             apiKey:'7bb93464ea396b5c4394f00e6170ccea',
             TList:[],

        }


    },created(){
        0
    },

}
</script>

<style lang="scss">

</style>