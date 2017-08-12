<template>
  <section class="container">

    <h1>Test scss import bourbon</h1>

  </section>
</template>

<script>

</script>

<style lang="scss">
@import "~bourbon/app/assets/stylesheets/bourbon";

.container {
  @include linear-gradient(to top, red, orange);
}
</style>
