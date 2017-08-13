<template>
  <section class="container">

    <h1>bourbon icon bullet points</h1>

    <ul class="bullets">
      <li class="bullet">
        <div class="bullet-icon bullet-icon-1">
          <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/placeholder_square.png" alt="">
        </div>
        <div class="bullet-content">
          <h2>This Bullet Title</h2>
          <p>Lorem dolor sit amet consectetur adipisicing elit. Doloremque, minus, blanditiis, voluptatibus nulla quia ipsam sequi quos iusto aliquam iste magnam accusamus molestias quo illum impedit. Odit officia autem.</p>
          </div>
      </li>
      <li class="bullet">
        <div class="bullet-icon bullet-icon-2">
          <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/placeholder_square.png" alt="">
        </div>
        <div class="bullet-content">
          <h2>Another Bullet Title</h2>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque, minus, blanditiis, voluptatibus nulla quia ipsam sequi quos iusto aliquam iste magnam accusamus molestias quo illum.</p>
        </div>
      </li>
      <li class="bullet">
        <div class="bullet-icon bullet-icon-3">
          <img src="https://raw.githubusercontent.com/thoughtbot/refills/master/source/images/placeholder_square.png" alt="">
        </div>
        <div class="bullet-content">
          <h2>Last Bullet Title</h2>
          <p>Lorem ipsum sit amet consectetur adipisicing elit. Doloremque, minus, blanditiis, voluptatibus nulla quia ipsam sequi quos iusto aliquam iste magnam accusamus molestias quo illum impedit. Odit officia autem.</p>
        </div>
      </li>
    </ul>

  </section>
</template>

<script>

</script>

<style lang="scss">
@import "~bourbon/app/assets/stylesheets/bourbon";

.bullets {
  $base-line-height: 1.5em !default;
  $action-color: #477DCA !default;
  $dark-gray: #333 !default;
  $base-font-color: $dark-gray !default;
  $icon-bullet-size: 3.5em;

  display: flex;
  flex-wrap: wrap;
  margin: 1em;
  margin-bottom: $base-line-height;
  overflow: auto;
  padding: 0;

  .bullet {
    flex-basis: 20em;
    flex-grow: 1;
  }

  .bullet-icon {
    background: $action-color;
    border-radius: 50%;
    float: left;
    height: $icon-bullet-size;
    padding: $icon-bullet-size / 4;
    width: $icon-bullet-size;
  }

  .bullet-icon-1 {
    background: $action-color;
  }

  .bullet-icon-2 {
    background: adjust-hue($action-color, -50%);
  }

  .bullet-icon-3 {
    background: adjust-hue($action-color, -140%);
  }

  .bullet-content {
    margin-bottom: 2em;
    margin-left: $icon-bullet-size * 1.4;
  }

  h2 {
    border-bottom: 1px solid transparentize($base-font-color, 0.8);
    display: inline-block;
    font-size: $icon-bullet-size / 2.5;
    margin: 0 0 ($icon-bullet-size / 6) 0;
    padding-top: $icon-bullet-size / 7;
  }

  li {
    list-style: none;
  }

  p {
    color: $base-font-color;
    line-height: $base-line-height;
  }

  img {
    max-width: 100%;
  }
}
</style>
