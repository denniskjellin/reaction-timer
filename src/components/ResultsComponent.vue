<template>
  <div>
    <p>Reaction time - {{ score }} ms</p>
    <p :class="rankClass">{{ rank }}</p>
  </div>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank: null
    }
  },
  computed: {
    rankClass() {
      if (this.score < 250) {
        return 'f1-speed';
      } else if (this.score < 400) {
        return 'rapid-reflexes';
      } else {
        return 'snail-pace';
      }
    }
  },
  mounted() {
    if (this.score < 150) {
        this.rank = 'Wow! You are as fast as a F1 driver';
    } else if (this.score < 220) {
      this.rank = 'Impressive - but to slow for F1, maybe a rally driver?';
    } else if (this.score < 260) {
      this.rank = 'Not bad - but you need to work on your reflexes';
    } else {
      this.rank = 'Ouch! Snail Pace.. are you.. ok?';
    }
  }
}
</script>

<style>
  .f1-speed {
    font-size: 1.4em;
    color: green;
    font-weight: bold;
  }
  
  .rapid-reflexes {
    font-size: 1.4em;
    color: orange;
    font-weight: bold;
  }
  
  .snail-pace {
    font-size: 1.4em;
    color: red;
    font-weight: bold;
  }
</style>
