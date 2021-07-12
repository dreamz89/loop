<template>
  <div id="nav">
    <div class="links">
      <h4>ABOUT US</h4>
      <h4>GALLERY</h4>
      <h4>CREW</h4>
      <h4>CONTACT</h4>
    </div>
    <div class="logo">
      <img src="@/assets/segel-team-logo.png">
    </div>
  </div>
</template>

<style lang="scss" scoped>
#nav {
  display: flex;
  height: 86px;
  width: 100%;

  .links {
    background-color: $white;
    display: flex;
    align-items: center;
    padding: 0 40px;
    width: 100%;

    h4 {
      cursor: pointer;
      margin-right: 40px;

      &:hover {
        color: $red;
      }
    }
  }


  .logo {
    @include center;

    background-color: $red;
    height: 100%;
    width: 100%;
    max-width: 456px;
  }
}
</style>
