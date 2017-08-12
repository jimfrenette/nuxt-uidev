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

> Bourbon
```bash
# bourbon
npm install --save bourbon
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