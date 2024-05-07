<template>
  <div class="horizontal-cell-list">
    <SquareCell
      v-for="(number, index) in numbers"
      :key="index"
      :number="number"
      :size="cellSize"
      :border-radius="borderRadius"
    />
  </div>
</template>

<script>
import SquareCell from './SquareCell.vue';

export default {
  components: {
    SquareCell,
  },
  props: {
    numbers: Array,
    cellSize: Number,
    borderRadius: {
      type: Number,
      default: 10,
    },
  },
};
</script>

<style scoped>
.horizontal-cell-list {
  display: flex;
}
</style>
