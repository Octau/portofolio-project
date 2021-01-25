<template>
  <div id="app">
  <b-navbar toggleable="sm" type="light" variant="light" fixed="top">
    <b-navbar-toggle target="nav-text-collapse"></b-navbar-toggle>

    <b-navbar-brand>Octavius Young  |  Portofolio Website</b-navbar-brand>

    <b-collapse id="nav-text-collapse" is-nav>
      <b-navbar-nav>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>

    <b-carousel
      id="carousel-1"
      fade
      v-model="slide"
      :interval="3000"
      background="#ccc"
      img-width="100%"
      img-height="100vh"
      style="text-shadow: 1px 1px 2px #000;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <!-- Text slides with image -->
      <b-carousel-slide
        img-src="https://picsum.photos/1024/480/?image=52"
      ></b-carousel-slide>

      <!-- Slides with custom text -->
      <b-carousel-slide img-src="https://picsum.photos/1024/480/?image=54">
      </b-carousel-slide>

      <!-- Slides with image only -->
      <b-carousel-slide img-src="https://picsum.photos/1024/480/?image=58"></b-carousel-slide>

      <!-- Slides with img slot -->
      <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
      <b-carousel-slide>
        <template v-slot:img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="https://picsum.photos/1024/480/?image=55"
            alt="image slot"
          >
        </template>
      </b-carousel-slide>

      <!-- Slide with blank fluid image to maintain slide aspect ratio -->
      <b-carousel-slide caption="Blank Image" img-blank img-alt="Blank image">
      </b-carousel-slide>
    </b-carousel>
  <b-navbar class="bottom-navbar p-0" toggleable="sm" type="light" variant="light" fixed="bottom">
    <b-navbar-toggle target="nav-text-collapse"></b-navbar-toggle>

    <!-- <b-navbar-brand>BootstrapVue</b-navbar-brand> -->

    <b-collapse id="nav-text-collapse" is-nav>
      <b-navbar-nav v-b-hover="buttonHover">
        <b-nav-item class="pt-0 mx-auto">ABOUT</b-nav-item>
        <b-nav-item class="pt-0 mx-auto">ABOUT</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        slide: 0,
        sliding: null,
        isHovered: false,
      }
    },
    methods: {
      onSlideStart() {
        this.sliding = true;
      },
      onSlideEnd() {
        this.sliding = false;
      },
      buttonHover(hovered) {
        this.isHovered = hovered;
      }
    }
  }
</script>

<style lang="scss">
    @import "./assets/scss/index.scss";
</style>