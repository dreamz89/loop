<template>
  <div id="modal">
    <div class="content">
      <div class="static-top"></div>
      <div class="scrollable">
        <div class="top">
          <div class="date">
            <img src="@/assets/icon-calendar-gray.png" />
            <h5>23 MAI 2021</h5>
          </div>
          <div class="article">
            <div class="left">
              <h2>NEWSARTIKEL HEADLINE</h2>
              <h4>LOREM IPSUM PROIN GRAVIDA NIBH VEL VELIT</h4>
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Maecenas eget ullamcorper tortor. Sed venenatis fringilla nisi
                eget sodales. Aliquam rhoncus enim et mauris laoreet, ut
                eleifend mauris iaculis. Nullam blandit mauris tellus, pulvinar
                elementum mauris cursus nec. Ut ornare suscipit malesuada.
                Mauris mattis nisi et ante lacinia, in maximus odio vulputate.
                Praesent a imperdiet quam. Etiam vulputate porta ullamcorper.
                Sed pretium mauris ac enim porta, et faucibus risus tempus.
                Integer lacus odio, euismod in tempor sit amet, luctus eu
                turpis.
              </p>
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Maecenas eget ullamcorper tortor. Sed venenatis fringilla nisi
                eget sodales. Aliquam rhoncus enim et mauris laoreet, ut
                eleifend mauris iaculis. Nullam blandit mauris tellus, pulvinar
                elementum mauris cursus nec. Ut ornare suscipit malesuada.
                Mauris mattis nisi et ante lacinia, in maximus odio vulputate.
                Praesent a imperdiet quam. Etiam vulputate porta ullamcorper.
                Sed pretium mauris ac enim porta, et faucibus risus tempus.
                Integer lacus odio, euismod in tempor sit amet, luctus eu
                turpis.
              </p>
            </div>
            <div class="right"></div>
          </div>
        </div>
        <div class="bottom">
          <h4>ÄLTERE ARTIKEL</h4>
        </div>
      </div>
      <div class="icons">
        <div class="close" @click="$emit('close-modal')">
          <img src="@/assets/icon-cross.svg" />
        </div>
        <div class="social-media">
          <div class="facebook" />
        </div>
        <div class="social-media">
          <div class="twitter" />
        </div>
        <div class="social-media">
          <div class="google" />
        </div>
      </div>
    </div>
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
  flex-direction: column;
  justify-content: center;

  .content {
    margin: 0 100px;
    height: fit-content;
    max-height: 100%;
    width: fit-content;
    max-width: 1200px;
    position: relative;

    .static-top {
      background-color: $white;
      height: 86px;
      width: 100%;
    }

    .scrollable {
      height: calc(100% - 86px);
      overflow: auto;

      .top {
        background-color: $white;
        padding: 0 70px 72px;

        .date {
          display: flex;
          align-items: flex-end;
          margin-bottom: 45px;

          > img {
            height: 30px;
            width: 30px;
          }

          h5 {
            color: $gray;
            line-height: 15px;
            margin: 0 0 0 8px;
          }
        }

        .article {
          display: flex;

          .left {
            h2 {
              margin: 0;
            }

            h4 {
              margin: 0 0 40px;
              padding: 20px 0;
              border-bottom: 1px solid $gray;
            }

            p {
              color: $gray;
            }
          }
        }
      }

      .bottom {
        background-color: $off-white;
        padding: 38px 70px 56px;

        h4 {
          color: $red;
        }
      }
    }

    .icons {
      position: absolute;
      top: 86px;
      right: -100px;
      width: 100px;
      cursor: pointer;

      .close {
        background-color: $off-white;
        height: 100px;

        @include center;

        img {
          height: 30px;
          width: 30px;
        }
      }

      .social-media {
        background-color: $black;
        height: 100px;

        @include center;

        > div {
          background-color: $white;
          mask-repeat: no-repeat;
          height: 30px;
          width: 30px;
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

        .google {
          mask-image: url(../assets/social-google-plus.svg);

          &:hover {
            background-color: $google;
          }
        }
      }
    }
  }
}
</style>