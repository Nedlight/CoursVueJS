<template>
  <div id="app">
    <contenue></contenue>
    <header-top></header-top>
  </div>
</template>

<script>

import contenue from './components/Contenue.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    'contenue' : contenue,
    'header-top' : Header
  }
}
</script>

<style>

</style>
