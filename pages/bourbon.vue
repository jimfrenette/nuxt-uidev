<template>
  <section class="container">

    <h1>Test scss import bourbon</h1>

  </section>
</template>

<script>

</script>

<style lang="scss">
@import "~bourbon/app/assets/stylesheets/bourbon";
@import "~bourbon-neat/app/assets/stylesheets/neat";

.container {
  @include linear-gradient(to top, red, orange);

  @include media(40em) {
    @include linear-gradient(to top, orange, red);
  }
}
</style>
