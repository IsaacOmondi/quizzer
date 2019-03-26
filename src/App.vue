<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
        <h1 class="text-center">The Quizzer</h1>
      </div>
    </div>
    <hr>
    <div class="row">
      <div class="col-xs-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
        <component :is="mode" @answered="answered($event)" @confirmed="mode = 'app-question'"></component>
      </div>
    </div>
  </div>
</template>

<script>
import Question from './components/Question';
import Answer from './components/Answer';


export default {
  data() {
    return{
      mode: 'app-question'
    }
  },
  methods: {
    answered(isCorrect) {
      if (isCorrect) {
        this.mode = 'app-answer';
      } else {
        this.mode = 'app-question';
        alert('Wrong, try again!');
      }
    }
  },
  components: {
    appQuestion: Question,
    appAnswer: Answer
  }
}
</script>

<style>

</style>
