<template>
  <div id="app">
    <VerticalCellList :data="cellData" :cellSize="cellSize" />
  </div>
</template>

<script>
import VerticalCellList from './components/VerticalCellList.vue';

export default {
  components: {
    VerticalCellList,
  },
  data() {
    return {
      cellData: [],
      cellSize: 50,
    };
  },
  created() {
    this.generateCellData();
  },
  methods: {
    generateCellData() {
      const rowCount = Math.floor(Math.random() * 100) + 101;
      // console.log('rowCount:', rowCount);
      this.cellData = [];
      for (let i = 0; i < rowCount; i++) {
        const innerNumbers = [];
        const innerCount = Math.floor(Math.random() * 10) + 11;
        // console.log('innerCount:', innerCount);
        for (let j = 0; j < innerCount; j++) {
          innerNumbers.push(Math.floor(Math.random() * 100));
        }
        this.cellData.push(innerNumbers);
      }
    },
  },
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
</style>
