<template>
  <div class="tops-wrap">
    <div class="tops-wrap-item">
      <span>图标</span>
      <span>1</span>
    </div>
    <div class="tops-wrap-item">
      <span>图标</span>
      <span>2</span>
    </div>
    <div class="tops-wrap-item">
      <span>图标</span>
      <span>3</span>
    </div>
    <div class="tops-wrap-item">
      <span>图标</span>
      <span>4</span>
    </div>
    <div class="tops-wrap-item">
      <span>图标</span>
      <span>5</span>
    </div>
    <div class="tops-wrap-item">
      <span>图标</span>
      <span>6</span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'tops',
}
</script>
<style lang="less" scoped>
.tops-wrap {
  height: 300px;
  background-color: #293f4e;
  width: 100%;
  color: #fff;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: flex-start;
  .tops-wrap-item {
    text-align: center;
    flex: 0 0 25%;
  }
}
</style>
