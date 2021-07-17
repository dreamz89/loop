<template>
  <div id="modal">
    <div class="content"></div>
  </div>
</template>

<style lang="scss" scoped>
#modal {
  position: fixed;
  z-index: 99;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.4);
      display: flex;
    justify-content: center;

  .content {
    background-color: $white;
    margin: 0 20px;
    padding: 86px 70px;
    height: fit-content;
    width: fit-content;
    max-width: 1200px;
  }
}
</style>