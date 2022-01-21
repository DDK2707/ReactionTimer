<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      Click Now!
      </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0,
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit('endGame', this.reactionTime)
        }
    }
}
</script>

<style>
    .block {
        width: 500px;
        border-radius: 15px;
        background: red;
        color: black;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>