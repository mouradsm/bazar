<template>
  <div id="app">
    <hello></hello>
    <formulario ></formulario>
  </div>
</template>

<script>

import formulario from './components/formulario.vue'
import hello from './components/hello.vue'

export default {
    data() {
        return {
            confirmation: true
        }
    },
    components: {
        formulario,
        hello
    }
}

</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
