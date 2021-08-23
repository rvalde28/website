<template>
  <div class="hello">
    <div class="topnav">
      <div class="top-left">
        <a class="active" href="#home">Home</a> <!-- hide at top, display if others are clicked-->
        <a href="#mission-statement">Mission Statement</a>
        <a href="#gallery">Our Work</a>
      </div>
      <div class="top-mid">
        <img class="mid-img" src="../assets/Logo.jpg" style="height: 60px;">
      </div>
      <div class="top-right">
        <a href="#footer">About Us</a>
      </div>
    </div>


    <vueper-slides id="home" fade :touchable="false" autoplay>
    <vueper-slide
      v-for="(slide, i) in slides"
      :key="i"
      :image="slide.image" />
    </vueper-slides>


    <!--mission statement -->
    <div id="mission-statement" class="stm">
    <div class="mission-stm-box"> 
      <div class="mission-stm">
      Mission Statemtent
      </div>
      <div class="mission-stm-desc">
      Sed lacinia, urna non tincidunt mattis, tortor neque adipiscing diam, a cursus ipsum ante quis turpis. Nulla facilisi. Ut fringilla. Suspendisse potenti. Nunc feugiat mi a tellus consequat imperdiet. Vestibulum sapien. Proin quam. Etiam ultrices. Suspendisse in justo eu magna luctus suscipit. Sed lectus. Integer euismod lacus luctus magna. Quisque cursus, metus vitae pharetra auctor, sem massa mattis sem, at interdum magna augue eget diam. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Morbi lacinia molestie dui. 
      </div>
    </div>
    </div>


    <div class="image-grid">
      <div id="gallery" class="gallery">
        <div class="gallery-panel" @click="showDynamicComponentModal(photo)" 
            v-for="photo in images"
            :key="photo.id">
          <img :src="photo.path">
        </div>
      </div>
    </div>

    <demo-adaptive-modal />

    <div id="footer" class="footer">
      <div class="footer-logo">
        <img src="../assets/logo-trans-white.png">
      </div>
      <div class="footer-info">

        <div class="footer-contact">
          <div>
            <span>Contact us</span>
          </div>
        </div>

        <div class="footer-clients">
          <div>
            <span> Our Clients</span>
          </div>
        </div>

      </div>
    </div>

  </div>
</template>

<script>
import { VueperSlides, VueperSlide } from 'vueperslides'
import DemoCustomComponent from './adaptive.vue'

import 'vueperslides/dist/vueperslides.css'

export default {
  components: { VueperSlides, VueperSlide },
  name: 'HelloWorld',
  methods: {
    showDynamicComponentModal(photo) {
      this.$modal.show(DemoCustomComponent, {
        photoObj: photo,
      })
    },
  },
  props: {
    msg: String
  },

  data: () => ({
  images: [
    {
      path: require('@/assets/image1.jpg'),
      description: "some image",
    },
    {
      path: require('@/assets/image2.jpg'),
      description: "some image",
    },
    {
      path: require('@/assets/image4.jpg'),
      description: "some image",
    },
    {
      path: require('@/assets/image5.jpg'),
      description: "some image",
    },
    {
      path: require('@/assets/image6.jpg'),
      description: "some image",
    },
    {
      path: require('@/assets/image7.jpg'),
      description: "some image",
    },
    {
      path: require('@/assets/image8.jpg'),
      description: "some image",
    },
  ],
  slides: [
  {
    title: 'El Teide Volcano, Spain',
    content: 'Photo by Max Rive',
    // You can also provide a URL for the image.
    image: require('@/assets/image1.jpg')
  },
  {
    title: 'El Teide Volcano, Spain',
    content: 'Photo by Max Rive',
    // You can also provide a URL for the image.
    image: require('@/assets/image2.jpg')
  },
  {
    title: 'El Teide Volcano, Spain',
    content: 'Photo by Max Rive',
    // You can also provide a URL for the image.
    image: require('@/assets/image3.jpg')
  },
  // Other slides.
  ]
  }),
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
