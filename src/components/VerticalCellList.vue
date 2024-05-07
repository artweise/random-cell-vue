<template>
  <div class="vertical-cell-list">
    <h1 class="page-title">Random Cells</h1>
    <div class="list-container">
      <HorizontalCellList
        v-for="(numbers, index) in data"
        :key="index"
        :numbers="numbers"
        :cellSize="cellSize"
        :borderRadius="borderRadius"
      />
    </div>
  </div>
</template>

<script>
import HorizontalCellList from './HorizontalCellList.vue';

export default {
  components: {
    HorizontalCellList,
  },
  props: {
    data: Array,
    cellSize: Number,
    borderRadius: {
      type: Number,
      default: 10,
    },
  },
};
</script>

<style scoped>
.vertical-cell-list {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  height: 100vh;
}

.page-title {
  text-align: center;
}

.list-container {
  width: 100%;
}
</style>
