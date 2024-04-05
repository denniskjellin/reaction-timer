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
        return 'ninja-fingers';
      } else if (this.score < 400) {
        return 'rapid-reflexes';
      } else {
        return 'snail-pace';
      }
    }
  },
  mounted() {
    if (this.score < 180) {
        this.rank = 'Wow! You are super the ultimate Ninja Fingers!';
    } else if (this.score < 250) {
      this.rank = 'Impressive - Ninja Fingers';
    } else if (this.score < 400) {
      this.rank = 'Rapid Reflexes!';
    } else {
      this.rank = 'Ouch! Snail Pace..';
    }
  }
}
</script>

<style>
  .ninja-fingers {
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
