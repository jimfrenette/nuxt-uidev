<template>
  <section class="container">

    <h1>bourbon accordion-tabs</h1>

    <ul class="accordion-tabs">
      <li class="tab-header-and-content">
        <a href="javascript:void(0)" class="is-active tab-link">Tab Item</a>
        <div class="tab-content">
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras tincidunt pellentesque lorem, id suscipit dolor rutrum id. Morbi facilisis porta volutpat. Fusce adipiscing, mauris quis congue tincidunt, sapien purus suscipit odio, quis dictum odio tortor in sem. Ut sit amet libero nec orci mattis fringilla. Praesent eu ipsum in sapien tincidunt molestie sed ut magna. Nam accumsan dui at orci rhoncus pharetra tincidunt elit ullamcorper. Sed ac mauris ipsum. Nullam imperdiet sapien id purus pretium id aliquam mi ullamcorper.</p>
        </div>
      </li>
      <li class="tab-header-and-content">
        <a href="javascript:void(0)" class="tab-link">Another Tab</a>
        <div class="tab-content">
          <p>Ut laoreet augue et neque pretium non sagittis nibh pulvinar. Etiam ornare tincidunt orci quis ultrices. Pellentesque ac sapien ac purus gravida ullamcorper. Duis rhoncus sodales lacus, vitae adipiscing tellus pharetra sed. Praesent bibendum lacus quis metus condimentum ac accumsan orci vulputate. Aenean fringilla massa vitae metus facilisis congue. Morbi placerat eros ac sapien semper pulvinar. Vestibulum facilisis, ligula a molestie venenatis, metus justo ullamcorper ipsum, congue aliquet dolor tortor eu neque. Sed imperdiet, nibh ut vestibulum tempor, nibh dui volutpat lacus, vel gravida magna justo sit amet quam. Quisque tincidunt ligula at nisl imperdiet sagittis. Morbi rutrum tempor arcu, non ultrices sem semper a. Aliquam quis sem mi.</p>
        </div>
      </li>
      <li class="tab-header-and-content">
        <a href="javascript:void(0)" class="tab-link">Third</a>
        <div class="tab-content">
          <p>Donec mattis mauris gravida metus laoreet non rutrum sem viverra. Aenean nibh libero, viverra vel vestibulum in, porttitor ut sapien. Phasellus tempor lorem id justo ornare tincidunt. Nulla faucibus, purus eu placerat fermentum, velit mi iaculis nunc, bibendum tincidunt ipsum justo eu mauris. Nulla facilisi. Vestibulum vel lectus ac purus tempus suscipit nec sit amet eros. Nullam fringilla, enim eu lobortis dapibus, quam magna tincidunt nibh, sit amet imperdiet dolor justo congue turpis.</p>
        </div>
      </li>
      <li class="tab-header-and-content">
        <a href="javascript:void(0)" class="tab-link">Last Item</a>
        <div class="tab-content">
          <p>Sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Phasellus dui urna.</p>
        </div>
      </li>
    </ul>

  </section>
</template>

<script>
import $ from 'jquery'

export default {
  mounted: () => {
    $('.accordion-tabs').each(function (index) {
      $(this).children('li').first().children('a').addClass('is-active').next().addClass('is-open').show()
    })

    $('.accordion-tabs').on('click', 'li > a.tab-link', function (event) {
      if (!$(this).hasClass('is-active')) {
        event.preventDefault()
        var accordionTabs = $(this).closest('.accordion-tabs')
        accordionTabs.find('.is-open').removeClass('is-open').hide()

        $(this).next().toggleClass('is-open').toggle()
        accordionTabs.find('.is-active').removeClass('is-active')
        $(this).addClass('is-active')
      } else {
        event.preventDefault()
      }
    })
  }
}
</script>

<style lang="scss">
@import "~bourbon/app/assets/stylesheets/bourbon";
@import "~bourbon-neat/app/assets/stylesheets/neat";

.accordion-tabs {
  $base-border-color: #dcdcdc !default;
  $base-border-radius: 3px !default;
  $base-background-color: #fff !default;
  $base-spacing: 1.5em !default;
  $action-color: #477dca !default;
  $dark-gray: #333 !default;
  $light-gray: #ddd !default;
  $medium-screen: 40em !default;
  $tab-border: 1px solid $base-border-color;
  $tab-content-background: lighten($light-gray, 10);
  $tab-active-background: $tab-content-background;
  $tab-inactive-color: $base-background-color;
  $tab-inactive-hover-color: darken($light-gray, 5);
  $tab-mode: $medium-screen;

  @include clearfix;
  line-height: 1.5;
  margin-bottom: $base-spacing;
  padding: 0;

  @include media(max-width $tab-mode) {
    border: $tab-border;
    border-radius: $base-border-radius;
  }

  .tab-header-and-content {
    list-style: none;

    @include media($tab-mode) {
      display: inline;
    }

    &:first-child .tab-link {
      border-top-left-radius: $base-border-radius;
      border-top-right-radius: $base-border-radius;

      @include media(max-width $tab-mode) {
        border-top: 0;
      }
    }

    &:last-child .tab-link {
      @include media(max-width $tab-mode) {
        border-bottom-left-radius: $base-border-radius;
        border-bottom-right-radius: $base-border-radius;
      }
    }
  }

  .tab-link {
    background-color: $tab-inactive-color;
    border-top: $tab-border;
    color: $dark-gray;
    display: block;
    font-weight: bold;
    padding: ($base-spacing / 2) ($gutter / 2);
    text-decoration: none;

    @include media($tab-mode) {
      @include border-top-radius($base-border-radius);
      border-top: 0;
      display: inline-block;
    }

    &:hover {
      color: $action-color;
    }

    &:focus {
      outline: none;
    }

    &.is-active {
      background-color: $tab-active-background;

      @include media($tab-mode) {
        background-color: $tab-active-background;
        border: $tab-border;
        border-bottom-color: $tab-active-background;
        margin-bottom: -1px;
      }
    }
  }

  .tab-content {
    background: $tab-content-background;
    display: none;
    padding: $base-spacing $gutter;
    width: 100%;

    @include media($tab-mode) {
      border: $tab-border;
      border-bottom-left-radius: $base-border-radius;
      border-bottom-right-radius: $base-border-radius;
      border-top-right-radius: $base-border-radius;
      float: left;
    }
  }
}
</style>
