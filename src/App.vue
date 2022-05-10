<template>
  <div id="app">
    <header>
    <AppHeader/>
    </header>
    <main>
      <AppMain/>
    </main>

  </div>
</template>

<script>
    
import AppHeader from './components/AppHeader.vue'



export default {
  name: 'App',
  components: {
    AppHeader,
    
  }
}
</script>

<style lang="scss">
@import './style/general.scss';

</style>
