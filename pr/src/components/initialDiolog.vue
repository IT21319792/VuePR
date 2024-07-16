<template>
<div>
    <div class="container">
        <div class="row">
        <div class="col-md-12">
            <h1>Ask a Question</h1>
           <div class="mb=3">
                <input
                    name="question"
                    type="text"
                    class="form-control"
                    id="question"
                    placeholder="Enter your question"
                    v-model="question"
                />
         

           </div>
            <button
             @click="nextScreen" 
             class="btn"
             v-if = "question"
           
             
             >Next</button>
        </div>
        </div>
    </div>

</div> 
</template>

<script>
export default {
    data(){
        return{
            question:''
        }
    },
    methods:{
        nextScreen(e){
            this.$emit('nextScreen',this.question);
            e.preventDefault();
            console.log('button triggered');
        }
    }
}

</script>


