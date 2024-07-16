<template>

<div class="container">

</div>

<component
  :is="screens[position]"
  :question="question"
  @goto="handleGoTo"
  @question="handleQuestion"
  @goNext="handleGoNext"
  @goBack="handleGoBack"

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
    },
    handleGoNext(position){
      this.position = position;
    },
    handleGoBack(position){
      this.position = position;
    }
  }

}

</script>

<style>
  @import './assets/style.css';
</style>
