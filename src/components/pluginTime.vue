<template>

    <div class="box pluginTime-move-animation">
      <div class="item" :class="{ shake: disabled }">
        pluginTime
        <div :class="{ shake: disabled }">
          <button @click="warnDisabled">Click me</button>
          <span v-if="disabled">This feature is disabled!</span>
        </div>

      </div>
    </div>

</template>

<script>
export default {
  name: 'pluginTime',
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

<style>
.pluginTime-move-animation {
  animation-name: growing, pluginTime-move, wiggle;
  animation-duration: 1.3s, 1.3s, 1.3s;
  animation-delay: 0s, 1.3s, 2.6s;
  animation-iteration-count: 1, 1, 1;
  animation-fill-mode: forwards, forwards, forwards;
}
@keyframes pluginTime-move {
  0% {
    position: fixed;
    top: 60%;
    left: calc(50% - 300px);
    right: calc(50% - 300px);
    z-index: 9999;
  }
  100% {
    position: fixed;
    top: 320px;
    right: 10px;
    z-index: 9999;
  }
}
</style><style scoped>
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
  background-color:#7c49a8;
}
.box .item{
  width: 300px;
  height: 300px;
  border: 1px solid #2c3e50;
}
</style>
