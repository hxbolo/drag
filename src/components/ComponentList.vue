<template>
  <div @dragstart="handleDragstrat" class="component-list">
    <div
      v-for="(item, index) in componentList"
      :key="index"
      class="list"
      draggable
      :data-index="index"
    >
      <i :class="item.icon"></i>
      <span>{{ item.label }}</span>
    </div>
  </div>
</template>
<script>
import componentList from './custom-component/component-list'
export default {
  data() {
    return {
      componentList,
    }
  },
  methods: {
    handleDragstrat(e) {
      console.log(e.target.dataset.index)
      // TODO ???这个是拿到index  存去哪里？
      e.dataTransfer.setData('index', e.target.dataset.index)
    },
  },
}
</script>
<style lang="less" scoped>
.component-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    padding: 10px;

    .list {
        width: 45%;
        border: 1px solid #ddd;
        cursor: grab;
        margin-bottom: 10px;
        text-align: center;
        color: #333;
        padding: 2px 5px;
    }
}
</style>