<template>
  <div class="flex jc-ct container" id="app">
    <div class="plugin flex flex-direc-column plugin-left">
      <cpu class="plugin-item"/>
      <hd class="plugin-item"/>
      <mem class="plugin-item"/>
    </div>
    <div class="plugin flex flex-direc-column plugin-center">
      <terminal class="plugin-center"/>
    </div>
    <div class="plugin flex flex-direc-column plugin-right">
      <net class="plugin-item"/>
      <task class="plugin-item"/>
      <pluginTime class="plugin-item"/>
    </div>
  </div>
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
  }
}
</script>

<style>
@import 'styles/animation.css';
@import 'styles/common.css';

.container {
  min-width: 1000px;
  width: 100%;
  min-height: calc(100vh - 50px);
}

.plugin {

}

.plugin-left {
  -webkit-flex: 2;
  flex: 2;
  /*background-color: aqua;*/
  min-width: 310px;
}

.plugin-center {
  /*-webkit-flex: 3;*/
  /*flex: 3;*/
  width: 100%;
  height: 100%;
  /*background-color: blue;*/
}

.plugin-right {
  -webkit-flex: 2;
  flex: 2;
  /*background-color: brown;*/
  min-width: 310px;
}

.plugin-item {
  width: 310px;
  height: 310px;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
