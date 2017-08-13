<template>
  <section class="container">

    <h1>bourbon cards</h1>

    <div class="cards">
      <div class="card">
        <div class="card-image">
          <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/mountains.png" alt="">
        </div>
        <div class="card-header">
          First Card
        </div>
        <div class="card-copy">
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fuga, officiis sunt neque facilis culpa molestiae necessitatibus delectus veniam provident.</p>
        </div>
      </div>

      <div class="card">
        <div class="card-image">
          <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/mountains-4.png" alt="">
        </div>
        <div class="card-header">
          Another Card
        </div>
        <div class="card-copy">
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fuga, officiis sunt neque facilis culpa molestiae necessitatibus delectus veniam provident.</p>
        </div>
      </div>

      <div class="card">
        <div class="card-image">
          <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/mountains-3.png" alt="">
        </div>
        <div class="card-header">
          The Last Card
        </div>
        <div class="card-copy">
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
        </div>
      </div>
    </div>

  </section>
</template>

<script>

</script>

<style lang="scss">
@import "~bourbon/app/assets/stylesheets/bourbon";
@import "~bourbon-neat/app/assets/stylesheets/neat";

.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.card {
  $base-border-color: gainsboro !default;
  $base-border-radius: 3px !default;
  $base-background-color: white !default;
  $base-spacing: 1.5em !default;
  $action-color: #477DCA !default;
  $dark-gray: #333 !default;
  $base-font-color: $dark-gray !default;
  $card-border-color: $base-border-color;
  $card-border: 1px solid $card-border-color;
  $card-background: lighten($card-border-color, 10%);
  $card-header-background: $card-background;
  $card-margin: 1em;
  $card-image-hover-opacity: 0.7;
  $card-image-hover-color: #F8F2B4;

  background-color: $card-background;
  border: $card-border;
  border-radius: $base-border-radius;
  box-shadow: 0 2px 4px darken($base-background-color, 10%);
  cursor: pointer;
  flex-basis: 15em;
  flex-grow: 1;
  margin: 0 $card-margin $base-spacing $card-margin;
  position: relative;
  transition: all 0.2s ease-in-out;

  .card-image {
    background-color: $card-image-hover-color;
    height: 150px;
    max-height: 150px;
    overflow: hidden;

    img {
      @include border-top-radius($base-border-radius);
      opacity: 1;
      transition: all 0.2s ease-in-out;
      width: 100%;
    }
  }

  .card-header {
    background-color: $card-header-background;
    border-bottom: $card-border;
    border-radius: $base-border-radius $base-border-radius 0 0;
    font-weight: bold;
    line-height: 1.5em;
    padding: ($base-spacing / 3) ($base-spacing / 2);
    transition: all 0.2s ease-in-out;
  }

  .card-copy {
    font-size: 0.9em;
    line-height: 1.5em;
    padding: ($base-spacing / 2) ($base-spacing / 2);

    p {
      margin: 0 0 ($base-spacing / 2);
    }
  }

  &:focus,
  &:hover {
    cursor: pointer;

    img {
      opacity: $card-image-hover-opacity;
    }
  }

  &:active {
    background-color: $card-background;

    .card-header {
      background-color: $card-background;
    }
  }
}
</style>
