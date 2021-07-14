<template>
  <div id="article">
    <h2>Headline - Lorem Ipsum</h2>
    <h4>Subtitle Lorem Ipsum</h4>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas eget ullamcorper tortor. Sed venenatis fringilla nisi eget sodales. Aliquam rhoncus enim et mauris laoreet, ut eleifend mauris iaculis. Nullam blandit mauris tellus, pulvinar elementum mauris cursus nec. Ut ornare suscipit malesuada. Mauris mattis nisi et ante lacinia, in maximus odio vulputate. Praesent a imperdiet quam. Etiam vulputate porta ullamcorper. Sed pretium mauris ac enim porta, et faucibus risus tempus. Integer lacus odio, euismod in tempor sit amet, luctus eu turpis.
    <br><br>
      Second paragraph Ut molestie justo magna. Donec a mauris quis arcu ultricies viverra et in erat. Quisque libero metus, ullamcorper vel lacinia ut, pharetra in nisl. Aenean orci est, tincidunt a lectus sed, hendrerit pretium lorem. Curabitur rhoncus tincidunt odio, ut pellentesque metus ultrices hendrerit. Nunc pulvinar fermentum est, et varius quam fringilla sit amet. Fusce et imperdiet sem. Aenean mattis lacus eu nunc placerat, ut dapibus tortor mattis. Aliquam dolor purus, vestibulum eget suscipit eget, rutrum a augue. Etiam porttitor sem nec diam blandit accumsan.
    <br><br>
      Third paragraph Aliquam venenatis dolor augue, et venenatis ligula ultrices id. Nulla facilisis libero vehicula sem efficitur, vitae vestibulum massa ornare. Pellentesque placerat vel turpis sit amet imperdiet. Nam et arcu euismod, lacinia purus id, pellentesque felis. Quisque lacinia ac tellus vel ultricies. Integer nec sem sit amet sapien tristique consectetur ut vel ligula. Ut enim urna, fermentum eu luctus at, ullamcorper ut dolor. Duis scelerisque vestibulum nulla in lacinia.
    <br><br>
      Forth paragraph Nunc tincidunt iaculis tempus. Donec egestas volutpat massa, ac consectetur lacus ornare efficitur. Sed at odio libero. Nam hendrerit auctor justo. Morbi elementum est id sollicitudin mollis. Nullam vel neque gravida, ullamcorper magna nec, posuere tellus. Suspendisse elementum, libero sit amet pulvinar mattis, sapien enim luctus est, quis porttitor metus erat sed odio. In dignissim porta ultrices. Nullam vel consequat tortor. Ut nulla magna, suscipit faucibus neque quis, tempor tincidunt tortor. Maecenas volutpat arcu vel erat finibus iaculis. Nulla purus lacus, sollicitudin in neque feugiat, consequat ullamcorper urna. Mauris ac elementum mauris. Donec vel est nulla. Sed a ligula purus. Quisque ut porttitor est, eu condimentum eros.
    <br><br>
      Fifth paragraph Proin ut velit maximus dolor varius euismod ac ac quam. Cras vitae suscipit lacus, vitae faucibus ligula. Proin pharetra mattis nulla, a ornare velit varius vitae. In hac habitasse platea dictumst. Cras orci odio, accumsan vel maximus in, hendrerit nec quam. In iaculis, ante id laoreet finibus, quam sem vulputate urna, at gravida nisi urna vulputate nibh. Vivamus varius tellus posuere orci rhoncus, ut tincidunt elit commodo. Proin porta leo ac purus aliquet molestie. Donec molestie vestibulum massa sed sollicitudin. Curabitur mollis nisl sed nisl vehicula, eget ultricies lectus efficitur. Morbi ornare augue sed leo viverra faucibus.
    </p>
    <div class="timeline">
      <img src="@/assets/timeline.png" />
      <svg viewBox="0 0 100 12">
        <polygon points="0,12 100,0 100,12" />
      </svg>
    </div>
  </div>
</template>

<style lang="scss" scoped>
#article {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: $white;
  padding-top: 50px;

  h2, h4 {
    margin: 0;
    text-transform: uppercase;
  }

  h2 {
    padding: 0 20px;
    text-align: center;
  }

  h4 {
    padding: 20px 30px;
    border-bottom: 1px solid $gray;
  }

  p {
    color: $gray;
    column-gap: 50px;
    column-width: 400px;
    margin: 40px 0 0;
    padding: 0 150px;

    @media (max-width: 1150px) {
      padding: 0 50px;
    }

    @media (max-width: 950px) {
      max-width: 500px;
    }
  }

  .timeline {
    position: relative;
    overflow: hidden;
    width: 100%;

    img {
      position: relative;
      width: 100%;
      z-index: 1;
    }

    svg {
      fill: $black;
      position: absolute;
      bottom: 0;
      left: 0;
    }
  }
}
</style>