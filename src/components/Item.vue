<!-- Item.vue -->
<template>
  <div
    :style="itemStyle"
    @mousedown="startDrag"
    @mouseenter="hoverEffect = true"
    @mouseleave="hoverEffect = false"
    :class="{ 'hover-scale': hoverEffect }"
  >
    {{ name }}
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    x: Number,
    y: Number,
    width: Number,
    height: Number,
  },
  data() {
    return {
      isDragging: false,
      offsetX: 0,
      offsetY: 0,
      hoverEffect: false,
    };
  },
  computed: {
    itemStyle() {
      return {
        top: `${this.y}px`,
        left: `${this.x}px`,
        width: `${this.width}px`,
        height: `${this.height}px`,
        position: "absolute",
        background: "linear-gradient(135deg, #FF5722, #FFC107)",
        color: "white",
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        borderRadius: "15px",
        boxShadow: "0 8px 16px rgba(0, 0, 0, 0.3)",
        cursor: "pointer",
        transition: "transform 0.2s ease, box-shadow 0.2s ease",
        fontWeight: "bold",
      };
    },
  },
  methods: {
    startDrag(event) {
      this.isDragging = true;
      this.offsetX = event.clientX - this.x;
      this.offsetY = event.clientY - this.y;
      document.addEventListener("mousemove", this.onDrag);
      document.addEventListener("mouseup", this.stopDrag);
    },
    onDrag(event) {
      if (this.isDragging) {
        const newX = event.clientX - this.offsetX;
        const newY = event.clientY - this.offsetY;
        this.$emit("updatePosition", { name: this.name, x: newX, y: newY });
      }
    },
    stopDrag() {
      this.isDragging = false;
      document.removeEventListener("mousemove", this.onDrag);
      document.removeEventListener("mouseup", this.stopDrag);
    },
  },
};
</script>

<style scoped>
.hover-scale {
  transform: scale(1.1);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.35);
}
</style>
