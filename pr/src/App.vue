<template>
main app
<div class="container">

</div>

<component
  :is="screens[position]"
  @goto="handleGoTo"
  @question="handleQuestion"

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
      position:0,
      question:''
    }

  },
  methods:{
    handleGoTo(position){
      this.position = position;
    },
    handleQuestion(question){
      this.question = question;
    }
  }

}

</script>

<style>
  @import './assets/style.css';
</style>
