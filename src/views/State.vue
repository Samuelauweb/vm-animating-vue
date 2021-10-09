<template>
  <div>
    <!-- set the width of our <div> via style binding -->
    <div :style="{ width: tweenedNumber + 'px' }" class="bar">
      <span>{{ tweenedNumber.toFixed(0) }}</span> 
    </div>
    <p>Using GSAP to manipulate data, instead of directly on element, using <code>watch</code> (a built-in Vue component option), <code>gsap.to()</code> method and <code>.toFixed()</code></p>
  </div>
</template>

<script>
import gsap from 'gsap'
export default {
  data() {
    return {
      number: 0,
      tweenedNumber: 0
    }
  },
  watch: {
    number(newValue) {
      // animate our data
      gsap.to(this.$data, {
        duration: 1,
        ease: 'circ.out',
        tweenedNumber: newValue //  the "tweenedNumber" property on our data (on this.$data)
      })
    }
  },
  methods: {
    randomNumber() {
      this.number = Math.floor(Math.random() * (800 - 0))
    } // updates number data with a new value (ranging from 0-800)
  },
  created() {
    setInterval(this.randomNumber, 1500)
  } // runs randomNumber() method every 1500ms
}
</script>

<style scoped>
.bar {
  padding: 5px;
  background-color: #2c3e50;
  border: 1px #16c0b0 solid;
  min-width: 20px;
}
.bar span {
  color: white;
}

code {
  background: lightcoral;
  color: white;
  padding: 2px;
}
</style>
