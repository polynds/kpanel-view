<template>

  <div class="box" :class="{ pluginTime_move_animation:anima }">
    <div class="item">
      pluginTime
    </div>
  </div>

</template>

<script>
export default {
  name: 'pluginTime',
  props: ['anima'],
  data () {
    return {}
  },
  methods: {}
}
</script>

<style scoped>
.pluginTime_move_animation {
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
    top: 320px;
    right: 10px;
    z-index: 9999;
  }
}
</style>
