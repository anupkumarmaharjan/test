<template>
  <div id="app">
    <HandsonTable />
    <!-- <DraggablePanel /> -->
    <app-draggable></app-draggable>
  </div>
</template>

<script>
import HandsonTable from './components/HandsonTable.vue'
import DraggablePanel from './components/DraggablePanel.vue'

export default {
  name: 'App',
  components: {
    HandsonTable,
    'app-draggable' : DraggablePanel,
  },
}
</script>

<style lang="scss" scoped>
   @import 'assets/scss/main.scss'
</style>
