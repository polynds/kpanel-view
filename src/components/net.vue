<template>

  <div class="box" :class="{ net_move_animation:anima }">
    <div class="item">
      net
    </div>
  </div>

</template>

<script>
export default {
  name: 'net',
  props: ['anima'],
  data() {
    return {}
  },
  methods: {}
}
</script>

<style scoped>
.net_move_animation {
  animation-name: growing, net-move, wiggle;
  animation-duration: 1.3s, 1.3s, 1.3s;
  animation-delay: 0s, 1.3s, 2.6s;
  animation-iteration-count: 1, 1, 1;
  animation-fill-mode: forwards, forwards, forwards;
}

@keyframes net-move {
  0% {
    position: fixed;
    top: 60%;
    left: calc(50% - 300px);
    right: calc(50% - 300px);
    z-index: 9999;
  }
  100% {
    top: 10px;
    right: 10px;
    z-index: 9999;
  }
}
</style>
