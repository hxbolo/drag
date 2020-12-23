
<template>
  <div class="home">
    <div class="herder">
      <el-button @click="undo">撤消</el-button>
      <el-button @click="redo">重做</el-button>
      <label for="input" class="insert">插入图片</label>
      <input type="file" @change="handleFileChange" id="input" hidden />
      <el-button @click="preview" style="margin-left: 10px">预览</el-button>
      <el-button @click="save">保存</el-button>
      <el-button @click="clearCanvas">清空画布</el-button>
      <div class="canvas-config">
        <span>画布大小</span>
        <input v-model="canvasStyleData.width" />
        <span>*</span>
        <input v-model="canvasStyleData.height" />
      </div>
    </div>

    <div class="main">
      <div class="left">
        <ComponentList />
      </div>
      <div class="center">
        <div class="centent">cneternt</div>
      </div>
      <div class="right">right</div>
    </div>
  </div>
</template>
<script>
import ComponentList from '@/components/ComponentList' // 左侧列表组件
export default {
  components:{
    ComponentList
  },
  data() {
    return {
      canvasStyleData: {
        width: 1200,
        height: 800,
      },
    }
  },
  methods: {
    undo() {},
    redo() {},
    handleFileChange() {},
    preview() {},
    save() {},
    clearCanvas() {},
  },
}
</script>
<style lang="less" scoped>
.home {
  height: 100vh;
  background-color: #fff;
}
.herder {
  height: 64px;
  line-height: 64px;
  background: #fff;
  border-bottom: 1px solid #ddd;
}

.canvas-config {
  display: inline-block;
  margin-left: 10px;
  font-size: 14px;
  color: #606266;
}
.canvas-config span {
  margin-left: 10px;
}
.canvas-config input {
  width: 50px;
  margin-left: 10px;
  outline: none;
  padding: 0 5px;
  border: 1px solid #ddd;
  color: #606266;
}
.main {
  position: relative;
  height: calc(100% - 64px);
  .left {
    position: absolute;
    width: 200px;
    height: 100%;
    left: 0;
    top: 0;
    padding-top: 10px;
  }
  .right {
    position: absolute;
    height: 100%;
    width: 262px;
    right: 0;
    top: 0;
  }
  .center {
    margin-left: 200px;
    margin-right: 262px;
    background: #f5f5f5;
    height: 100%;
    overflow: auto;
    padding: 20px;
    .centent {
      height: 100%;
      overflow: auto;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }
}
</style>