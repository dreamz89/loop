<template>
  <div id="footer">
    <div class="left">
      <p>© 2021. Segel-Team. Alle Rechte vorbehalten</p>
    </div>
    <div class="middle">
      <div class="twitter" />
      <div class="facebook" />
    </div>
    <div class="right">
      <p>Impressum</p>
      <p>Datenschutz</p>
      <p>Rechtliches</p>
      <p>Copyright</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
#footer {
  background-color: $off-white;
  display: flex; 
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
  height: 124px;
  width: 100%;

  // until max two lines of text
  @media (max-width: 525px) {
    flex-direction: column;
    justify-content: center;
    height: auto;

    .left {
      order: 3;
    }
  }

  .left {
    p {
      color: $gray;
      font-size: 13px;
      margin: 10px 20px;
    }
  }

  .middle {
    display: flex;

    > div {
      background-color: $black;
      cursor: pointer;
      margin: 10px;
      height: 25px;
      width: 25px;
    }

    .twitter {
      // in order to change color without inline-svg
      // does not work in IE
      mask-image: url(../assets/social-twitter.svg);

      &:hover {
        background-color: $twitter;
      }
    }

    .facebook {
      mask-image: url(../assets/social-facebook.svg);

      &:hover {
        background-color: $facebook;
      }
    }
  }

  .right {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;

    p {
      color: $black;
      cursor: pointer;
      font-size: 13px;
      margin: 0 10px;

      &:hover {
        color: $red;
      }
    }
  }
}
</style>