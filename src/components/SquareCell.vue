<template>
  <div
    class="square-cell"
    :class="[getClass(number), { 'is-hovered': isHovered }]"
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
  methods: {
    getClass(number) {
      if (number >= 1 && number <= 10) {
        return 'yellow-cell';
      } else if (number >= 11 && number <= 20) {
        return 'pink-cell';
      } else if (number >= 21 && number <= 30) {
        return 'aqua-cell';
      } else if (number >= 31 && number <= 40) {
        return 'orange-cell';
      } else if (number >= 41 && number <= 50) {
        return 'blue-cell';
      } else if (number >= 51 && number <= 60) {
        return 'violet-cell';
      } else if (number >= 61 && number <= 70) {
        return 'coral-cell';
      } else if (number >= 71 && number <= 80) {
        return 'lime-cell';
      } else if (number >= 81 && number <= 90) {
        return 'green-cell';
      } else {
        return 'default-cell';
      }
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
  color: #242424;
}

.square-cell.is-hovered {
  transform: scale(0.8);
}

.square-cell:hover {
  cursor: pointer;
}

.yellow-cell {
  background-color: #e5e8c0;
}

.pink-cell {
  background-color: #e8c0d1;
}

.aqua-cell {
  background-color: #c0e5e8;
}

.orange-cell {
  background-color: #e8c3c0;
}

.blue-cell {
  background-color: #d9edf8;
}

.violet-cell {
  background-color: #dedaf4;
}

.coral-cell {
  background-color: #ffcbcb;
}

.lime-cell {
  background-color: #f1f7b5;
}

.green-cell {
  background-color: #c9e4de;
}

.default-cell {
  background-color: #eae0da;
}
</style>
