<template>

  <div class="box" :class="{ cpu_move_animation:anima }">
    <div class="item">
      cpu
    </div>
  </div>

</template>

<script>
export default {
  name: 'cpu',
  props: ['anima'],
  data () {
    return {}
  },
  methods: {}
}
</script>

<style scoped>
.cpu_move_animation {
  animation-name: growing, cpu-move, wiggle;
  animation-duration: 1.3s, 1.3s, 1.3s;
  animation-delay: 0s, 1.3s, 2.6s;
  animation-iteration-count: 1, 1, 1;
  animation-fill-mode: forwards, forwards, forwards;
}

@keyframes cpu-move {
  0% {
    position: fixed;
    top: 60%;
    left: calc(50% - 300px);
    right: calc(50% - 300px);
    z-index: 9999;
    display: block;
  }
  100% {
    top: 10px;
    left: 10px;
    z-index: 9999;
    display: block;
  }
}
</style>
