<template>

  <div>
    <div ref="terminal" id="terminal"></div>
  </div>

</template>
<script>

import {Terminal} from 'xterm'
import {FitAddon} from 'xterm-addon-fit'
import {AttachAddon} from 'xterm-addon-attach'
import {WebLinksAddon} from 'xterm-addon-web-links'
import 'xterm/css/xterm.css'

export default {
  name: 'WebShell',
  data () {
    return {
      scoket: '',
      term: null
    }
  },
  methods: {
    debounce (fn, wait) {
      let timeout = null
      return function () {
        if (timeout !== null) clearTimeout(timeout)
        timeout = setTimeout(fn, wait)
      }
    },
    resizeScreen () {
      this.fitAddon.fit()
      this.socket.send(JSON.stringify([this.term.cols, this.term.rows]))
    }
  },
  mounted () {
    this.term = new Terminal({
      cursorBlink: true
    })
    this.term.write('Hello from \x1B[1;3;31mxterm.js\x1B[0m $ ')
    this.fitAddon = new FitAddon()
    this.term.loadAddon(this.fitAddon)
    this.term.loadAddon(new WebLinksAddon())
    this.term.open(this.$refs.terminal)
    this.fitAddon.fit()
    this.term.focus()
    this.socket = new WebSocket(`ws://127.0.0.1:8888/k8swebssh/qa/guangyin/qa-gycoop-java-6d888ccf55-hzbbz?cols=${this.term.cols}&rows=${this.term.rows}'`)
    const attachAddon = new AttachAddon(this.socket)
    this.term.loadAddon(attachAddon)
    window.addEventListener('resize', this.debounce(this.resizeScreen, 1500), false)
  }
}

</script>
