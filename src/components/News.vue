<template>
  <div id="news">
    <div class="hero"></div>
    <div class="headline">
      <h1>Lorem Ipsum Proin Gravi</h1>
      <h4>
        Lorem Ipsum. Proin gravida nibh vel velit auctor aliquet. Aenean
        Solliciudin, lorem
      </h4>
    </div>
    <div class="group">
      <div class="left">
        <div class="news-light" @click="isModalOpen = true">
          <div>
            <img src="@/assets/icon-calendar-gray.png" />
            <h5>23 MAI 2021</h5>
          </div>
          <h4>NEWS HEADLINE</h4>
          <p>
            Lorem Ipsum. Proin gravida nibh vel velit auctor aliquet. Aenean
            Solliciudin...
          </p>
        </div>
        <div class="news-dark" @click="isModalOpen = true">
          <div>
            <img src="@/assets/icon-calendar-gray.png" />
            <h5>23 MAI 2021</h5>
          </div>
          <h4>NEWS HEADLINE</h4>
          <p>
            Lorem Ipsum. Proin gravida nibh vel velit auctor aliquet. Aenean
            Solliciudin...
          </p>
        </div>
        <img src="@/assets/square-image.jpg" />
      </div>
      <div class="right">
        <div class="news-top">
          <h2>17 MAI</h2>
          <h3>HEADLINE BEITRAG 2021</h3>
          <h4>SUBTITLE</h4>
          <p>
            Lorem Ipsum.Proin gravida nibh vel velit auctor aliquet. Aenean
            solliciudin, lorem quis bibendum auctor.
          </p>
        </div>
        <div class="news-bottom">
          <h2>03 OKT</h2>
          <h3>HEADLINE BEITRAG 2021</h3>
          <h4>SUBTITLE</h4>
          <p>
            Lorem Ipsum.Proin gravida nibh vel velit auctor aliquet. Aenean
            solliciudin, lorem quis bibendum auctor.
          </p>
        </div>
        <img src="@/assets/small-square-image-1.jpg" />
        <img src="@/assets/small-square-image-2.jpg" />
      </div>
      <div class="pictures">
        <img src="@/assets/icon-news.svg" />
        <h3>NEWS+ BILDER</h3>
      </div>
      <div class="calendar">
        <img src="@/assets/icon-calendar-white.png" />
        <h3>SEGELTEAM TERMINE 2021</h3>
      </div>
    </div>
    <Modal v-if="isModalOpen" />
  </div>
</template>

<script>
import Modal from "../components/Modal.vue";

export default {
  components: {
    Modal,
  },
  data() {
    return {
      isModalOpen: false,
    };
  },
  mounted() {
    document.addEventListener("click", this.onClickOutside);
  },
  beforeDestroy() {
    document.removeEventListener("click", this.onClickOutside);
  },
  methods: {
    onClickOutside(e) {
      if (e.target.id === "modal") {
        this.isModalOpen = false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
#news {
  position: relative;

  .hero {
    background: url("../assets/hero.png");
    @include background;
    background-position: center bottom;
    height: 800px;
  }

  .headline {
    max-width: 550px;
    text-align: center;
    text-transform: uppercase;
    position: absolute;
    top: 150px;
    right: 20px;

    h1 {
      color: $red;
      margin: 24px 0;
    }
  }

  @media (max-width: 1200px) {
    .hero {
      height: 600px;
    }

    .headline {
      max-width: 490px;
      top: 80px;
      right: 20px;
    }
  }

  @media (max-width: 1100px) {
    .headline {
      max-width: 400px;
      top: 120px;
      right: 20px;

      h1 {
        font-size: 3.1rem;
      }

      h4 {
        font-size: 0.94rem;
      }
    }
  }

  @media (max-width: 900px) {
    .hero {
      height: 500px;
    }

    .headline {
      top: 110px;
      right: 10px;
    }
  }

  @media (max-width: $tablet) {
    .headline {
      background-color: rgba($white, 0.4);
    }
  }

  @media (max-width: $mobile) {
    .headline {
      background-color: unset;
      position: static;
    }
  }

  .group {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(500px, 1fr));
    grid-template-rows: repeat(4, 1fr);
    align-items: flex-start;

    @media (max-width: 1000px) {
      grid-template-columns: repeat(auto-fill, minmax(50vw, 1fr));
    }

    @media (max-width: $tablet) {
      grid-template-rows: repeat(2, 1fr);
    }

    .left {
      grid-row: span 3;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      grid-template-rows: repeat(3, 1fr);
      height: 100%;

      @media (max-width: 1000px) {
        grid-template-columns: repeat(auto-fit, minmax(25vw, 1fr));
      }

      @media (max-width: $tablet) {
        grid-template-columns: repeat(auto-fit, minmax(50vw, 1fr));
        grid-template-rows: repeat(2, 280px);
        grid-column: span 2;
        grid-row: span 2;
      }

      @media (max-width: $mobile) {
        grid-template-rows: repeat(3, minmax(200px, 1fr));
      }

      .news-light {
        background-color: $off-white;

        &:hover {
          background-color: rgba($off-white, 0.7);
        }
      }

      .news-dark {
        background-color: $black;

        &:hover {
          background-color: rgba($black, 0.9);
        }

        p {
          color: $white;
        }
      }

      .news-light,
      .news-dark {
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        padding: 25px;
        cursor: pointer;

        @media (max-width: $mobile) {
          grid-column: span 2;
        }

        > div {
          display: flex;
          align-items: flex-end;

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

        h4 {
          color: $red;
          margin: 10px 0;
        }

        p {
          margin: 0;
        }
      }

      > img {
        grid-column: span 2;
        grid-row: span 2;
        object-fit: cover;
        height: 100%;
        width: 100%;

        @media (max-width: $tablet) {
          grid-row: span 1;
        }
      }
    }

    .right {
      grid-row: span 3;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      grid-template-rows: 1fr 1fr 1fr;
      height: 100%;

      @media (max-width: 1000px) {
        grid-template-columns: repeat(auto-fit, minmax(25vw, 1fr));
      }

      @media (max-width: $tablet) {
        grid-template-columns: repeat(auto-fit, minmax(50vw, 1fr));
        grid-template-rows: repeat(3, 280px);
        grid-column: span 2;
        grid-row: span 3;
      }

      @media (max-width: $mobile) {
        grid-template-rows: repeat(3, minmax(200px, 1fr));
      }

      .news-top {
        background: url("../assets/map-1.jpg");
      }

      .news-bottom {
        background: url("../assets/map-2.jpg");
      }

      .news-top,
      .news-bottom {
        @include background;

        grid-column: span 2;
        padding: 25px;

        h2 {
          margin: 0 0 20px 0;

          @media (max-width: $mobile) {
            font-size: 1.88rem;
          }
        }
        h3 {
          color: $red;
          margin: 0;

          @media (max-width: $mobile) {
            font-size: 1.25rem;
          }
        }
        h4 {
          margin: 12px 0 16px 0;

          @media (max-width: $mobile) {
            font-size: 0.94rem;
          }
        }
        p {
          margin: 0;
          max-width: 400px;
        }
      }

      > img {
        object-fit: cover;
        height: 100%;
        width: 100%;
      }
    }

    .pictures {
      background: url("../assets/triangle-image.jpg");
      @include background;
      text-align: center;
      height: 280px;
      width: 100%;

      @include center;
      flex-direction: column;

      @media (max-width: $mobile) {
        grid-column: span 2;
        height: 200px;
      }

      h3 {
        color: $white;
        margin: 20px 20px 0;
        width: 120px;

        @media (max-width: $mobile) {
          font-size: 1.25rem;
        }
      }
    }

    .calendar {
      background-color: $black;
      height: 280px;
      width: 100%;

      @include center;
      flex-direction: column;

      @media (max-width: $mobile) {
        grid-column: span 2;
        height: 200px;
      }

      h3 {
        color: $white;
        margin: 20px 20px 0;
        text-align: center;
        width: 230px;

        @media (max-width: $mobile) {
          font-size: 1.25rem;
        }
      }
    }
  }
}
</style>