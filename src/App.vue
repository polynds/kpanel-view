<template>
  <div class="container" id="app">
    <div class="plugin plugin-left">
      <cpu class="plugin-item" :anima="cpu_anima"/>
      <hd class="plugin-item" :anima="hd_anima"/>
      <mem class="plugin-item" :anima="mem_anima"/>
    </div>
    <div class="plugin plugin-center">
      <terminal class="plugin-center"/>
    </div>
    <div class="plugin plugin-right">
      <net class="plugin-item" :anima="net_anima"/>
      <task class="plugin-item" :anima="pluginTime_anima"/>
      <pluginTime class="plugin-item" :anima="task_anima"/>
    </div>
  </div>
  <!--  <div class="flex jc-ct container" id="app">-->
  <!--    <div class="plugin flex flex-direc-column plugin-left">-->
  <!--      <cpu class="plugin-item"/>-->
  <!--      <hd class="plugin-item"/>-->
  <!--      <mem class="plugin-item"/>-->
  <!--    </div>-->
  <!--    <div class="plugin flex flex-direc-column plugin-center">-->
  <!--      <terminal class="plugin-center"/>-->
  <!--    </div>-->
  <!--    <div class="plugin flex flex-direc-column plugin-right">-->
  <!--      <net class="plugin-item"/>-->
  <!--      <task class="plugin-item"/>-->
  <!--      <pluginTime class="plugin-item"/>-->
  <!--    </div>-->
  <!--  </div>-->
</template>

<script>
import cpu from './components/cpu'
import hd from './components/hd'
import mem from './components/mem'
import net from './components/net'
import task from './components/task'
import pluginTime from './components/pluginTime'
import terminal from './components/terminal'

export default {
  name: 'App',
  components: {
    cpu,
    hd,
    mem,
    net,
    task,
    pluginTime,
    terminal
  },
  data () {
    return {
      cpu_anima: false,
      hd_anima: false,
      mem_anima: false,
      net_anima: false,
      pluginTime_anima: false,
      task_anima: false
    }
  },
  mounted () {
    this.animate()
  },
  methods: {
    animate () {
      this.cpu_anima = true
      let that = this
      setTimeout(function () {
        that.net_anima = true
      }, 1500)
      setTimeout(function () {
        that.hd_anima = true
      }, 3000)
      setTimeout(function () {
        that.pluginTime_anima = true
      }, 5000)
      setTimeout(function () {
        that.mem_anima = true
      }, 7000)
      setTimeout(function () {
        that.task_anima = true
      }, 9000)
    }
  }
}
</script>

<style>
@import 'styles/animation.css';
@import 'styles/common.css';

.container {
  min-width: 1000px;
  width: 100%;
  display: flex;
}

.plugin {
  /*flex-flow: column;*/
  /*display: flex;*/

}

.plugin-item {
  flex: 1;
  display: flex;
}

.plugin-left {
  width: 250px;
  min-width: 250px;
  float: left;
}

.plugin-center {
  flex: 1;
  text-align: center;
  height: 100%;
}

.plugin-right {
  width: 250px;
  min-width: 250px;
  float: right;
}

.plugin-left, .plugin-right {
  width: 260px;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
