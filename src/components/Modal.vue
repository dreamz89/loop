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
            <div class="right">
              <div class="article-image">
                <div class="arrow-left">
                  <img src="@/assets/icon-arrow-left.svg" />
                </div>
                <img src="@/assets/modal-current-article.jpg" />
                <div class="arrow-right">
                  <img src="@/assets/icon-arrow-right.svg" />
                </div>
              </div>
              <h5>1/10</h5>
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
          </div>
        </div>
        <div class="bottom">
          <h4>ÄLTERE ARTIKEL</h4>
          <div class="arrow-left" />
          <div class="old-articles">
            <div class="old-article">
              <img src="@/assets/modal-old-article-1.jpg" />
              <h4>HEADLINE VON EINEM ÄLTEREN ARTIKEL</h4>
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Maecenas eget ullamcorper tortor. Sed venenatis fringilla nisi
                eget sodales. Aliquam rhoncus enim et mauris laoreet, ut
                eleifend mauris iaculis.
              </p>
            </div>
            <div class="old-article">
              <img src="@/assets/modal-old-article-2.jpg" />
              <h4>HEADLINE VON EINEM ÄLTEREN ARTIKEL</h4>
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Maecenas eget ullamcorper tortor. Sed venenatis fringilla nisi
                eget sodales. Aliquam rhoncus enim et mauris laoreet, ut
                eleifend mauris iaculis.
              </p>
            </div>
            <div class="old-article">
              <img src="@/assets/modal-old-article-3.jpg" />
              <h4>HEADLINE VON EINEM ÄLTEREN ARTIKEL</h4>
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Maecenas eget ullamcorper tortor. Sed venenatis fringilla nisi
                eget sodales. Aliquam rhoncus enim et mauris laoreet, ut
                eleifend mauris iaculis.
              </p>
            </div>
            <div class="old-article">
              <img src="@/assets/modal-old-article-4.jpg" />
              <h4>HEADLINE VON EINEM ÄLTEREN ARTIKEL</h4>
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Maecenas eget ullamcorper tortor. Sed venenatis fringilla nisi
                eget sodales. Aliquam rhoncus enim et mauris laoreet, ut
                eleifend mauris iaculis.
              </p>
            </div>
          </div>
          <div class="arrow-right" />
        </div>
      </div>
      <div class="logo">
        <img src="@/assets/segel-team-logo.png" />
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
  padding: 20px 20px 0;

  @media (max-width: $mobile) {
    padding: 10px;
  }

  .content {
    margin: 0 auto;
    height: fit-content;
    max-height: 100%;
    width: 100%;
    max-width: 1200px;
    position: relative;

    .static-top {
      background-color: $white;
      height: 86px;
      width: calc(100% - 100px);
    }

    .scrollable {
      height: calc(100% - 86px);
      width: calc(100% - 100px);
      overflow: auto;

      @media (max-width: $tablet) {
        width: calc(100% - 70px);
      }

      .top {
        background-color: $white;
        padding: 20px 70px 72px;

        @media (max-width: $tablet) {
          padding: 20px 40px 40px;
        }

        @media (max-width: $mobile) {
          padding: 20px;
        }

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
          display: grid;
          grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
          grid-gap: 20px;

          @media (max-width: 500px) {
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
          }

          .left {
            h2 {
              margin: 0;
              word-break: break-word;
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

          .right {
            .article-image {
              position: relative;
              width: 100%;

              .arrow-left,
              .arrow-right {
                @include verticallyCentered;
                @include centerChildren;
                background-color: rgba($black, 0.3);
                padding: 5px;
                cursor: pointer;

                img {
                  height: 20px;
                  width: 20px;
                }
              }
              .arrow-left {
                left: 15px;
              }
              .arrow-right {
                right: -15px;
              }

              img {
                width: 100%;
              }
            }

            h5 {
              margin: 0 0 50px;
              text-align: end;
            }

            p {
              color: $gray;
            }
          }
        }
      }

      .bottom {
        background-color: $off-white;
        padding: 56px 70px;
        position: relative;

        @media (max-width: $tablet) {
          padding: 40px;
        }

        h4 {
          color: $red;
          margin: 0 0 28px;
        }

        .arrow-left,
        .arrow-right {
          @include verticallyCentered;
          height: 25px;
          width: 25px;
          cursor: pointer;
        }

        .arrow-left {
          mask-image: url(../assets/icon-arrow-left.svg);
          background-color: $black;
          left: 33px;

          @media (max-width: $tablet) {
            left: 20px;
          }
        }
        .arrow-right {
          mask-image: url(../assets/icon-arrow-right.svg);
          background-color: $black;
          right: 10px;

          @media (max-width: $tablet) {
            right: -4px;
          }
        }

        .old-articles {
          display: flex;
          overflow: scroll;

          .old-article {
            min-width: 200px;
            max-width: 222px;
            margin-right: 24px;

            &:last-of-type {
              margin-right: 0;
            }

            img {
              width: 100%;
            }
            h4 {
              margin: 12px 0;
            }
            p {
              color: $gray;
            }
          }
        }
      }
    }

    .logo {
      @include centerChildren;

      position: absolute;
      top: 0;
      right: 0;
      background-color: $red;
      height: 86px;
      width: 100%;
      max-width: 456px;
      padding: 0 20px;
    }

    .icons {
      position: absolute;
      top: 86px;
      right: 0;
      width: 100px;
      cursor: pointer;

      @media (max-width: $tablet) {
        width: 70px;
      }

      .close {
        @include centerChildren;

        background-color: $off-white;
        height: 100px;

        @media (max-width: $tablet) {
          width: 70px;
        }

        img {
          height: 30px;
          width: 30px;
        }
      }

      .social-media {
        background-color: $black;
        height: 100px;

        @include centerChildren;

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