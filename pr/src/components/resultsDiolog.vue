<!-- 3rd page -->
<template>
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h1>Answer to Your Question</h1>
          <div class="mb-3">
            <p>{{ answer }}</p>
            <button @click="askNewQuestion" class="btn">Ask Another Question</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['question'],
    data() {
      return {
        answer: '',
        answers: [
          'It depends on various factors.',
          'That’s a great question! Let me think...',
          'The answer might surprise you.',
          'In most cases, it is true.',
          'Let’s explore the possibilities together.',
          'I would say the chances are high.',
          'Absolutely!',
          'No, not really.',
          'It’s hard to say for sure.',
          'Yes, that’s correct.'
        ]
      };
    },
    created() {
      this.provideAnswer();
    },
    methods: {
      provideAnswer() {
        const randomIndex = Math.floor(Math.random() * this.answers.length);
        this.answer = this.answers[randomIndex];
      },
      askNewQuestion() {
        this.$emit('goto', 0);
      }
    }
  };
  </script>
  