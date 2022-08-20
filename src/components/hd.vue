<template>

    <div class="box">
      <div class="item" :class="{ shake: disabled }">
        hd
        <div :class="{ shake: disabled }">
          <button @click="warnDisabled">Click me</button>
          <span v-if="disabled">This feature is disabled!</span>
        </div>

      </div>
    </div>

</template>

<script>
export default {
  name: 'hd',
  data () {
    return {
      disabled: false
    }
  },
  methods: {
    warnDisabled () {
      this.disabled = true
      setTimeout(() => {
        this.disabled = false
      }, 1500)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.shake {
  animation: shake 0.82s cubic-bezier(0.36, 0.07, 0.19, 0.97) both;
  transform: translate3d(0, 0, 0);
}

@keyframes shake {
  10%,
  90% {
    transform: translate3d(-1px, 0, 0);
  }
  20%,
  80% {
    transform: translate3d(2px, 0, 0);
  }
  30%,
  50%,
  70% {
    transform: translate3d(-4px, 0, 0);
  }
  40%,
  60% {
    transform: translate3d(4px, 0, 0);
  }
}

.box{
  width: 300px;
  height: 300px;
  background-color:transparent;
}
.box .item{
  width: 300px;
  height: 300px;
  border: 1px solid #2c3e50;
}
</style>
