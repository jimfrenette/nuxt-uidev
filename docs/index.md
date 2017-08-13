# vue-ui setup

> Sass loader

``` bash
# install sass loader
npm install sass-loader node-sass --save-dev
```

usage
```
<style lang="scss">
.container {
  h1 {
    color: red;
  }
}
</style>
```

> jQuery

``` bash
# jQuery
npm install jquery --save-dev
```

usage
```
<script>
import $ from 'jquery'

export default {
  mounted: () => {

    // jQuery code

  }
}
</script>
```

> Bourbon
```bash
# bourbon
npm install bourbon --save-dev
```

usage
```
<style lang="scss">
@import "~bourbon/app/assets/stylesheets/bourbon";

.container {
  @include linear-gradient(to top, red, orange);
}
</style>
```

> Bourbon Neat
```bash
# bourbon neat
npm install bourbon-neat --save-dev
```

usage
```
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
```
