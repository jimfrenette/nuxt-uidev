<template>
  <section class="container">

    <h1>bourbon flex boxes</h1>

    <div class="flex-boxes">
      <a href="javascript:void(0)" class="flex-box flex-box-big">
        <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/placeholder_square.png" alt="">
        <h1 class="flex-title">A Wide Flex Box Item</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad nostrum, libero! Laborum distinctio necessitatibus voluptates eaque officiis, unde illo, earum voluptatum rerum, reiciendis ipsa ex dolorem a dicta, maxime aliquam.</p>
      </a>
      <a href="javascript:void(0)" class="flex-box">
        <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/placeholder_square.png" alt="">
        <h1 class="flex-title">Flex Box Item</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Harum molestiae fugiat tenetur fugit atque dignissimos, fugiat natus vitae.</p>
      </a>
      <a href="javascript:void(0)" class="flex-box">
        <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/placeholder_square.png" alt="">
        <h1 class="flex-title">A Flex Box Item</h1>
        <p>Lorem adipisicing elit. Voluptas consectetur tempora quis nam, officia tenetur blanditiis in illo dolor?</p>
      </a>
      <a href="javascript:void(0)" class="flex-box flex-box-big">
        <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/placeholder_square.png" alt="">
        <h1 class="flex-title">Another Wide Item</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quae quis ipsum, officia, aperiam tenetur dolor molestiae voluptate perferendis dolorem vel ex, unde fugit blanditiis sapiente.</p>
      </a>
      <a href="javascript:void(0)" class="flex-box">
        <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/placeholder_square.png" alt="">
        <h1 class="flex-title">Flex Box Item</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Explicabo obcaecati in provident illo.</p>
      </a>
      <a href="javascript:void(0)" class="flex-box">
        <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/placeholder_square.png" alt="">
        <h1 class="flex-title">Last Flex Box Item</h1>
        <p>Lorem ipsum dolor sit amet, elit. Rem, illum.</p>
      </a>
    </div>

  </section>
</template>

<script>

</script>

<style lang="scss">
@import "~bourbon/app/assets/stylesheets/bourbon";

.flex-boxes {
  $base-border-radius: 3px !default;
  $base-background-color: white !default;
  $dark-gray: #333 !default;
  $light-gray: #DDD !default;
  $base-font-color: $dark-gray !default;
  $flex-box-border-color: $light-gray;
  $flex-box-border: 1px solid $flex-box-border-color;
  $flex-box-background: lighten($light-gray, 10%);
  $flex-box-gutter: 0.4em;
  $flex-box-width: 18em;
  $flex-box-color: transparentize($base-font-color, 0.3);
  $flex-box-top-colors:
    tomato,
    #72BFBF,
    #92B1E3,
    #E3D743,
    #CCC,
    #F6C05C;

  @include clearfix;
  align-items: stretch;
  clear: both;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  text-align: center;

  .flex-box {
    align-self: stretch;
    background: $flex-box-background;
    border-radius: $base-border-radius;
    box-shadow: inset 0 0 1px $flex-box-border-color, 0 2px 4px darken($base-background-color, 10%);
    display: block;
    flex: 2 2 15em;
    margin: $flex-box-gutter;
    padding: 2em 2em 3em 2em;
    text-decoration: none;
    transition: all 0.2s ease-in-out;

    @for $i from 1 to 7 {
// assign colors from $flex-box-top-colors list
      &:nth-child(#{$i}) {
        $color-from-list: nth($flex-box-top-colors, $i);
        border-top: 6px solid $color-from-list;

        &:focus,
        &:hover {
          background-color: transparentize($color-from-list, 0.9);
        }
      }
    }

    img {
      display: block;
      height: 3em;
      margin: 0 auto 1em;
      opacity: 0.4;
    }

    .flex-title {
      color: $flex-box-color;
      font-size: 1.2em;
      margin-bottom: 0.5em;
    }

    p {
      color: transparentize($flex-box-color, 0.1);
      line-height: 1.5em;
      margin: auto;
    }
  }

  .flex-box-big {
    flex: 1 1 40em;
  }
}
</style>
