<template>
  <div class="top-header">
    <div class="logo-wrapper">
      <logo-icon stroke="#fff" stroke-width="10"></logo-icon>
    </div>
    <div class="logo-text">
      <div class="cn-text">数据大盘</div>
      <div class="en-text">Data</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TopHeader'
}
</script>

<style lang="scss" scoped>
.top-header {
  display: flex;
  align-items: center;
  width: 100%;
  height: 100%;
  background: rgb(36, 31, 32);
  padding: 0 64px;
  box-sizing: border-box;

  //.logo {
  //  width: 100px;
  //  height: 100px;
  //}

  .logo-wrapper {
    width: 120px;
    height: 120px;
  }

  .logo-text {
    flex: 1;
    margin-left: 40px;

    .cn-text {
      color: rgb(255, 255, 255);
      font-weight: bold;
      font-size: 60px;
      letter-spacing: 2px;
    }

    .en-text {
      color: rgb(255, 255, 255);
      font-size: 36px;
      letter-spacing: 1px;
    }
  }
}
</style>
