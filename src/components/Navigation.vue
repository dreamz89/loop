<template>
  <div id="nav">
    <div class="hamburger" v-if="windowWidth <= 768">
      <img
        v-show="!showMobileNav"
        @click="showMobileNav = !showMobileNav"
        src="@/assets/icon-hamburger.svg"
      />
      <img
        v-show="showMobileNav"
        @click="showMobileNav = !showMobileNav"
        src="@/assets/icon-cross.svg"
      />
    </div>
    <div
      class="dropdown"
      :class="[showMobileNav ? 'show' : 'hide']"
      v-if="windowWidth <= 768"
    >
      <h5>ABOUT US</h5>
      <h5>GALLERY</h5>
      <h5>CREW</h5>
      <h5>CONTACT</h5>
    </div>
    <div class="links" v-if="windowWidth > 768">
      <h5>ABOUT US</h5>
      <h5>GALLERY</h5>
      <h5>CREW</h5>
      <h5>CONTACT</h5>
    </div>
    <div class="logo">
      <img src="@/assets/segel-team-logo.png" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showMobileNav: false,
      windowWidth: 0,
    };
  },
  mounted() {
    this.onResize();
    window.addEventListener("resize", this.onResize);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.onResize);
  },
  methods: {
    onResize() {
      this.windowWidth = window.innerWidth;
    },
  },
};
</script>

<style lang="scss" scoped>
#nav {
  display: flex;
  justify-content: space-between;
  height: 86px;
  width: 100%;

  .hamburger {
    display: flex;
    align-items: center;
    background-color: $white;
    padding: 0 30px;
    height: 100%;
    width: 100%;
    z-index: 2;

    img:first-of-type {
      cursor: pointer;
      height: 40px;
      width: 40px;
    }

    img:last-of-type {
      cursor: pointer;
      height: 30px;
      width: 30px;
      margin: 0 5px;
    }
  }

  .dropdown {
    background-color: $white;
    flex-direction: column;
    align-items: flex-start;
    position: absolute;
    top: 86px; // height of navbar
    left: 0;
    padding: 10px 40px;
    transition: all 0.3s;
    z-index: 1;

    h5 {
      cursor: pointer;
      margin: 30px 0;

      &:hover {
        color: $red;
      }
    }

    &.hide {
      transform: translateY(-250px);
    }

    &.show {
      transform: translateY(0px);
    }
  }

  .links {
    background-color: $white;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 40px;
    width: 100%;
    max-width: 510px;

    h5 {
      cursor: pointer;
      margin-right: 30px;
      white-space: nowrap;

      &:hover {
        color: $red;
      }

      &:last-child {
        margin-right: 0;
      }
    }
  }

  .logo {
    @include center;

    background-color: $red;
    height: 100%;
    width: 100%;
    max-width: 456px;
    padding: 0 20px;
    z-index: 3;

    img {
      @media (max-width: $mobile) {
        height: 30px;
      }
    }
  }
}
</style>
