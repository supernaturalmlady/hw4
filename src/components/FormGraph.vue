<template>
  <div class="form-graph">
    <div class="x-axis">
      <h2 class="x-axis__title">X</h2>
      <input
        v-model="columnData.columnName"
        type="text"
        placeholder="Column name"
      />
    </div>
    <div class="y-axis">
      <h2 class="y-axis__title">Y</h2>
      <input
        v-model="columnData.columnHeight"
        type="number"
        placeholder="Column height (in percent)"
      />
    </div>
    <button
      @click="addColumn"
      v-if="columnData.columnHeight && columnData.columnName"
    >
      Add
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      columnData: [{ id: 0, columnHeight: '', columnName: '' }],
    }
  },

  methods: {
    addColumn() {
      this.$emit('add-column', this.columnData)
      this.columnData = [{ id: 0, columnHeight: '', columnName: '' }]
    },
  },
}
</script>

<style>
.form-graph {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: flex-end;
}

input,
button {
  padding: 10px;
  border: 0;
  box-shadow: 0 0 15px 4px rgba(0, 0, 0, 0.06);
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
