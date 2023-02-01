<template>
  <div class="app">
    <form-graph @add-column="addColumn"></form-graph>
    <draw-graph :columns="columns"></draw-graph>
  </div>
</template>

<script>
import DrawGraph from './components/DrawGraph.vue'
import FormGraph from './components/FormGraph.vue'

export default {
  components: {
    DrawGraph,
    FormGraph,
  },

  data() {
    return {
      columns: [],
    }
  },

  methods: {
    addColumn(columnData) {
      this.columns.push(columnData)
    },
  },
}
</script>

<style>
.app {
  max-width: 1050px;
  margin: 0 auto;
}
</style>
