<template>
  <div ref="container" class="bg">
    <el-button v-if="!isScreenshot" class="close" @click="close">关闭</el-button>
    <el-button v-else class="close" @click="htmlToImage">确定</el-button>
    <div class="canvas-contain">
      <div
        class="canvas"
        :style="{
          ...getCanvasStyle(canvasStyleData),
          width: changeStyleWidthScale(canvasStyleData.width) + 'px',
          height: changeStyleHeightScale(canvasStyleData.height) + 'px'
        }"
      >
      <ComponentWrapper 
        v-for="(item, index) in copyData"
        :key="index"
        :config="item"
      />
      </div>
    </div>
  </div>
</template>


<script>

</script>

<style lang="sass">


</style>