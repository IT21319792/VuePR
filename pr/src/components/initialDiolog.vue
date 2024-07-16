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

                <button
             @click="nextScreen" 
             class="btn"
             v-if = "question"
           
             
             >Next</button>

             <div v-if="error">
                     Please enter a valid question
             </div>
         

           </div>
            
        </div>
        </div>
    </div>

</div> 
</template>

<script>
export default {
    data(){
        return{
            question:'',
            error:false
        }
    },
    methods:{
        nextScreen(e){
            this.$emit('nextScreen',this.question);
            e.preventDefault();
            console.log('button triggered');
            if(this.question.length<=5){
                console.log('error');
                this.error = true;
            
               
                
            } else{
                    console.log('ok');
                    this.error = false; 
                    this.$emit('goto',1);
                    this.$emit('question',this.question);
                }
        }
    }
}

</script>


