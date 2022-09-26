<template>
  <div>
    <div class="toolbar">
      <el-button @click="undo">撤销</el-button>
      <el-button @click="redo">重做</el-button>
      <label for="input" class="insert">
        插入图片
        <input
        id="input"
        type="file"
        hidden
        @change="handleFileChange"
        >
      </label>

      <el-button style="margin-left: 10px;" @click="preview(false)">预览</el-button>
      <el-button @click="save">保存</el-button>
      <el-button @click="clearCanvas">清空画布</el-button>
      <el-button :disable="!areaData.components.length" @click="compose">组合</el-button>
      <el-button :disable="!curComponent || curComponent.isLock || curComponent.components != 'Group'" @click="decompose">
        拆分
      </el-button>

      <el-button :disable="!curComponent || curComponent.isLock" @click="lock">锁定</el-button>
      <el-button :disable="!curComponent || !curComponent.isLock" @click="unlock">解锁</el-button>
      <el-button @click="preview(true)">截图</el-button>

      <div class="canvas-config">
        <span>画布大小</span>
        <input v-model="canvasStyleData.width">
        <span>*</span>
        <input v-model="canvasStyleData.height">
      </div>

      <div class="canvas-config">
        <span>画布比例</span>
        <input v-model="scale" @input="handleScaleChange"> %
      </div>
    </div>

    <!-- 预览 -->
    <Preview v-if="isShowPreview" :is-screenshot="isScreenshot" @close="handlePreviewChange"></Preview>
  </div>
</template>


<script>
export default {

}
</script>

<style>

</style>