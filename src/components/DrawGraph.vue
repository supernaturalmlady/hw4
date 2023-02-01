<template>
  <div>
    <div class="draw-graph">
      <div class="graph__wrapper">
        <div
          v-for="column in columns"
          :key="column.id"
          class="column"
          :style="{
            height: `${column.columnHeight}%`,
            width: '10px',
            backgroundColor: 'blue',
          }"
        ></div>
      </div>
    </div>
    <div class="text__wrapper">
      <div class="column-text" v-for="column in columns" :key="column.id">
        {{ column.columnName }}
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    columns: {
      required: true,
      type: Array,
    },
  },
}
</script>
<style>
.draw-graph {
  display: flex;
  margin-top: 30px;
  border: 1px solid black;
  height: 70vh;
}

.graph__wrapper {
  display: flex;
  align-items: flex-end;
  overflow: hidden;
}

.text__wrapper {
  display: flex;
  font-weight: 500;
  font-size: 13px;
}

.column-text {
  margin: 5px 6px 0 10px;
  writing-mode: vertical-lr;
  text-transform: uppercase;
}

.column {
  margin: 0 10px 0 10px;
  border: 1px solid black;
}
</style>
