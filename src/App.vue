<template>
  <div id="app">
    <div class="wrapper wrapper-start">
      <cpu class="plugin"/>
      <hd class="plugin"/>
      <mem class="plugin"/>
    </div>
    <div class="wrapper">

    </div>
    <div class="wrapper wrapper-end">
      <net class="plugin"/>
      <task class="plugin"/>
      <pluginTime class="plugin"/>
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

export default {
  name: 'App',
  components: {
    cpu,
    hd,
    mem,
    net,
    task,
    pluginTime
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.wrapper {
  display: -webkit-flex;
  display: flex;
}

.wrapper-start {
  -webkit-flex-direction: column;
  flex-direction: column;
  -webkit-justify-content: flex-end;
  justify-content: flex-end;
}

.wrapper-end {
  -webkit-flex-direction: column;
  flex-direction: column;
  -webkit-justify-content: flex-end;
  justify-content: flex-end;
}

.wrapper .plugin {
  flex: 1;
  margin-bottom: 10px;
  -webkit-justify-content: space-between;
  justify-content: space-between;
}
</style>
