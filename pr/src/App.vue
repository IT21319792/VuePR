<template>
main app
<div class="container">

</div>

<component
  :is="screens[position]"
/>

 
</template>

<script>

import appInitial from './components/initialDiolog.vue';
import appConfirm from './components/confirmDiolog.vue';
import appResults from './components/resultsDiolog.vue';

export default{
  components:{

    appConfirm,
    appInitial,
    appResults



  },
  data(){
    return{
      screens:['appInitial','appConfirm','appResults'],
      position:0
    }

  }

}

</script>

<style>
  @import './assets/style.css';
</style>
