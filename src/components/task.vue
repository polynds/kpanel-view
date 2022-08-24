<template>

  <div class="box" :class="{ task_move_animation:anima }">
    <div class="item">
      task
    </div>
  </div>

</template>

<script>
export default {
  name: 'task',
  props: ['anima'],
  data () {
    return {}
  },
  methods: {}
}
</script>

<style scoped>
.task_move_animation {
  animation-name: growing, task-move, wiggle;
  animation-duration: 1.3s, 1.3s, 1.3s;
  animation-delay: 0s, 1.3s, 2.6s;
  animation-iteration-count: 1, 1, 1;
  animation-fill-mode: forwards, forwards, forwards;
}

@keyframes task-move {
  0% {
    position: fixed;
    top: 60%;
    left: calc(50% - 300px);
    right: calc(50% - 300px);
    z-index: 9999;
  }
  100% {
    top: 630px;
    right: 10px;
    z-index: 9999;
  }
}
</style>
