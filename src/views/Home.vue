<template>
  <div class="home">
    <main>
      <!-- 左侧组件列表 -->
      <section class="left">
        左侧组件列表
      </section>

      <!-- 中间画布 -->
      <section class="center">
        <div 
        class="content"
        @drop="handleDrop"
        ></div>
      </section>

      <!-- 右侧属性列表 -->
      <section class="right">
        右侧属性列表
      </section>
    </main>
  </div>
</template>

<script>
// @ is an alias to /src


export default {

}
</script>

<style lang="scss">
  .home {
    height: 400vh;
    background-color: #fff;

    main {
      height: calc(100% - 64px);
      position: relative;

      .left {
        position: absolute;
        height: 100%;
        width: 200px;
        left:0;
        top: 0;

        & > div {
          overflow: auto;

          & :first-child {
            border-bottom: 1px solid #ddd;
          }
        }
      }

      .right {
        position: absolute;
        height: 100%;
        width: 288px;
        right: 0;
        top: 0;

        .el-select {
          width: 100%;
        }
      }

      .center {
        margin-left: 200px;
        margin-right: 288px;
        background-color: #f5f5f5;
        height: 100%;
        overflow: auto;
        padding: 20px;

        .content {
          width: 100%;
          height: 100%;
          overflow: auto;
        }
      }
    }
    
    .placeholder {
        text-align: center;
        color: #333;
    }
    .global-attr {
        padding: 10px;
    }
  }

</style>
