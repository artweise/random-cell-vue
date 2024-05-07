<template>
  <div
    class="square-cell"
    :class="{ 'is-hovered': isHovered }"
    @mouseenter="isHovered = true"
    @mouseleave="isHovered = false"
  >
    {{ number }}
  </div>
</template>

<script>
export default {
  props: {
    number: Number,
    size: Number,
    borderRadius: {
      type: Number,
      default: 10,
    },
  },
  data() {
    return {
      isHovered: false,
    };
  },
  computed: {
    adjustedSize() {
      return this.isHovered ? this.size * 0.8 : this.size;
    },
  },
};
</script>

<style scoped>
.square-cell {
  width: 50px;
  height: 50px;
  border: 1px solid #ccc;
  border-radius: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: transform 0.3s ease;
}

.square-cell.is-hovered {
  transform: scale(0.8); 
}

.square-cell:hover {
  cursor: pointer;
}
</style>
