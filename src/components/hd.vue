<template>

  <div class="box" :class="{ hd_move_animation:anima }">
    <div class="item">
      hd
    </div>
  </div>

</template>

<script>
export default {
  name: 'hd',
  props: ['anima'],
  data() {
    return {}
  },
  methods: {}
}
</script>

<style scoped>
.hd_move_animation {
  animation-name: growing, hd-move, wiggle;
  animation-duration: 1.3s, 1.3s, 1.3s;
  animation-delay: 0s, 1.3s, 2.6s;
  animation-iteration-count: 1, 1, 1;
  animation-fill-mode: forwards, forwards, forwards;
}

@keyframes hd-move {
  0% {
    position: fixed;
    top: 60%;
    left: calc(50% - 300px);
    right: calc(50% - 300px);
    z-index: 9999;
  }
  100% {
    top: 320px;
    left: 10px;
    z-index: 9999;
  }
}
</style>
