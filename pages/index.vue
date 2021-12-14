<template>
  <div id="counter">
    Counter: {{ counter }}
    {{isZero}}
  </div>
  <button @click="countUp"> counter up </button>
  <button @click="countDown"> counter up </button>
</template>

<script language="ts">

const countUp = () => {
  this.counter++;
}
const countDown = () => {
  this.counter--;
}
const index = {
  data() {
    return {
      counter: 0
    }
  },
  beforeCreate() {
    console.log('bc')
  },
  created() {
    console.log('c')
  },
  beforeMount() {
    console.log('bm')
  },
  mounted() {
    console.log('m')
  },
  beforeUpdate() {
    console.log('bu')
  },
  updated() {
    console.log('u')
  },
  beforeUnmount() {
    console.log('bum')
  },
  unmounted() {
    console.log('um')
  },
  methods: {
    countUp() {  this.counter++; },
    countDown() {  this.counter--; },
  },
  computed: {
    isZero() {
      return this.counter === 0;
    }
  }
}
export default {
  name: 'counter',
  ...index,
}
</script>

<style scoped>

</style>
