<script setup>
import { Carousel, Navigation, Pagination, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

const myCarousel = ref(null)

const imageUrls = [
  '/01.jpg',
  '/02.jpg',
  '/03.jpg',
  '/04.jpg',
  '/05.jpg',
]

const nextSlide = () => {
  myCarousel.value.next()
}
const prevSlide = () => {
  myCarousel.value.prev()
}

onMounted(() => {
})
</script>

<template>
  <div p-6 m-3 sm:m-12 text-black dark:text-gray-50>
    <div text-center mb-8>
      <h1 text-4xl font-bold>
        Design solutions made easy
      </h1>
      <p mt-5 sm:mt-6 mx-3 sm:mx-14>
        With over ten years of experience in various design disciplines, I'm your one-stop shop for your design needs.
      </p>
    </div>

    <!-- GRID HERO ELEMENT -->
    <div grid grid-rows-6 sm:grid-rows-3 lg:grid-rows-2 lg:grid-cols-3 sm:grid-cols-2 grid-cols-1 gap-4 text-white>
      <!-- first column -->
      <div class="bg-[#755CDE] graphic-design" h-72 rounded-lg row-span-2 flex items-end>
        <div ml-5 mb-3>
          Graphic Design
        </div>
      </div>

      <!-- 2nd column -->
      <div row-span-2 h-72>
        <div grid grid-cols-2 grid-rows-2 gap-4 auto-rows-max>
          <div rounded-lg row-span-1 class="h-34 ui-ux bg-[#F6A560]" flex items-end>
            <div ml-5 mb-3>
              UI/UX
            </div>
          </div>
          <div bg-pink-400 rounded-lg class="h-34 apps" flex items-end>
            <div ml-5 mb-3>
              Apps
            </div>
          </div>
          <div bg-red-400 rounded-lg col-span-2 class="h-34 illustrations" flex items-end>
            <div ml-5 mb-3>
              Illustrations
            </div>
          </div>
        </div>
      </div>

      <!-- 3rd column -->
      <div class="photography" row-span-1 bg-teal-600 flex items-end rounded-lg>
        <div ml-5 mb-3>
          Photography
        </div>
      </div>
      <div row-span-1 bg-yellow-600 rounded-lg flex items-end class="motion-graphics">
        <div ml-5 mb-3>
          Motion Graphics
        </div>
      </div>
    </div>
    <!-- END GRID HERO ELEMENT -->

    <!-- photo plus info -->
    <div flex mt-16 flex-col md:flex-row gap-4>
      <div mb-4 flex-1 flex justify-center>
        <img src="/circle-portrait.png" alt="portrait">
      </div>
      <div px-6 flex-1>
        <h2 text-3xl font-bold mb-6>
          I’m Amy, and I’d love to work on your next project
        </h2>
        <p mb-6>
          I love working with others to create beautiful design solutions. I’ve designed everything from brand illustrations to complete mobile apps. I’m also handy with a camera!
        </p>
        <div text-center md:text-left>
          <button bg-red-400 px-8 py-3 rounded-full text-sm sm:text-xs class="text-[#FFF7F0]">
            Free Consultation
          </button>
        </div>
      </div>
    </div>
    <!-- end photo plus info -->

    <!-- carousel -->
    <div mt-12>
      <h2 mb-6 text-center text-3xl font-bold>
        My Work
      </h2>
      <Carousel bg-white ref="myCarousel" :items-to-show="1.5" :wrap-around="true">
        <Slide v-for="(imageUrl, index) in imageUrls" :key="index">
          <div class="carousel__item">
            <img :src="imageUrl" alt="image">
          </div>
        </Slide>
      </Carousel>

      <div flex justify-center gap-3 mt-6>
        <div rounded-full p-5 bg-black dark:bg-red-400 @click="prevSlide">
          <div i-carbon-arrow-left text-white dark:text-black />
        </div>
        <div rounded-full p-5 bg-black dark:bg-red-400 @click="nextSlide">
          <div i-carbon-arrow-right text-white dark:text-black />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.carousel__item {
  min-height: 200px;
  width: 100%;
  color:  var(--vc-clr-white);
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.carousel__slide {
  padding: 10px;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
  border: 5px solid white;
}

.graphic-design {
  background-position: top 10px right 10px;
  background-repeat: no-repeat;
  background-image: url('/graphic-design.svg');
  background-size: 35%;
}
.ui-ux {
  background-position: top 10px right 10px;
  background-repeat: no-repeat;
  background-image: url('/ui-ux.svg');
  background-size: 40%;
}
.apps {
  background-position: top 10px right 10px;
  background-repeat: no-repeat;
  background-image: url('/apps.svg');
  background-size: 40%;
}
.illustrations {
  background-position: top 10px right 10px;
  background-repeat: no-repeat;
  background-image: url('/illustrations.svg');
  background-size: 40%;
}
.photography {
  background-position: top 10px right 10px;
  background-repeat: no-repeat;
  background-image: url('/photography.svg');
  background-size: 40%;
}
.motion-graphics {
  background-position: top 10px right 10px;
  background-repeat: no-repeat;
  background-image: url('/motion-graphics.svg');
  background-size: 40%;
}

@media screen and (min-width: 640px) {
  .graphic-design, .ui-ux, .apps, .illustrations, .photography, .motion-graphics {
    background-size: 30%;
  }
}
</style>

<route lang="yaml">
meta:
  layout: home
</route>
