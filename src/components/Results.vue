<template>
    <h2>Reaction Time</h2>
  <p>{{ score }}</p>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if (this.score <300) {
            this.rank = "Sheeeeeeeeeeeeeesh"
        }
        else if (this.score <450) {
            this.rank = "Heyyy, that's pretty good"
        }
        else {
            this.rank = "bruh..."
        }
    }
}
</script>

<style>
.rank {
    font-size: 1.4em;
    color: tomato;
    font-weight: bold;
}
</style>