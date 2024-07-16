<template>
<div class="container">
    <h5>
        your question is:
    </h5>

    <div class="col-md-12">
    <div class="mb=3">
    <div >
        {{question}}
    </div>
    <div>
        <button
            @click="goNext"
            class="btn"
        >
            Next
        </button>
    </div>
    <div>
        <button
        @click = "goBack"
        class="btn"
        >
            Back
        </button>
    </div>
</div>

</div>
</div>



 
</template>

<script>
export default {
    props:['question'],
    methods:{
        goNext(){
            this.$emit('goto',2);
        },
        goBack(){
            this.$emit('goto',0);
        }
    }
}

</script>


