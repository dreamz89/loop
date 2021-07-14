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
  </div>
</template>

<style lang="scss" scoped>
#news {
  position: relative;

  .hero {
    background: url("../assets/hero.png");
    background-position: center bottom;
    background-repeat: no-repeat;
    background-size: cover;
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
}
</style>