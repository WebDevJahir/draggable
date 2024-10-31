<!-- Board.vue -->
<template>
  <div class="board">
    <Item v-for="(item, key) in items.data.items.movableItem.itemList" :key="key" :name="key" :x="item.x" :y="item.y"
      :width="item.w" :height="item.h" @updatePosition="updateItemPosition" />
  </div>
</template>

<script>
  import Item from "./Item.vue";

  export default {
    components: {
      Item,
    },
    data() {
      return {
        items: {
          data: {
            items: {
              movableItem: {
                totalItem: 4,
                itemList: {
                  "item-1": { h: 70, w: 70, x: 0, y: 0 },
                  "item-2": { h: 70, w: 70, x: 100, y: 0 },
                  "item-3": { h: 70, w: 70, x: 200, y: 0 },
                  "item-4": { h: 70, w: 70, x: 300, y: 0 },
                },
              },
            },
          },
        },
      };
    },
    methods: {
      updateItemPosition({ name, x, y }) {
        this.items.data.items.movableItem.itemList[name].x = x;
        this.items.data.items.movableItem.itemList[name].y = y;
      },
    },
  };
</script>

<style scoped>
  .board {
    position: relative;
    width: 780px;
    height: 400px;
    background: linear-gradient(145deg, #6DD5FA, #2980B9);
    border: 3px solid #0288D1;
    border-radius: 20px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 15px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
  }
</style>