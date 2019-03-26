<template>
    <div class="alert alert-success tex-center">
        <h3>That's Correct!</h3>
        <hr>
        <button class="btn btn-primary" @click="onNextQuestion">Next Question</button>
    </div>
</template>

<script>
export default {
    methods: {
        onNextQuestion() {
            this.$emit('confirmed');
        }
    }
}
</script>

<style>

</style>
