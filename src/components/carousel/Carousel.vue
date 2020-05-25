<template>
      <b-carousel
      id="carousel-fade"
      fade
      :interval="4000"
      controls
    >
      <!-- Text slides with image -->
        <b-carousel-slide 
        v-for="(slide, index) in carouselSlides()" 
        :key="index"
        :caption="slide.title"
        :style="{ backgroundImage: 'url(' + require(`../../assets/${slide.image}`) + ')' }"
        >
        </b-carousel-slide>

        <!-- <a href="" v-for="(slide, index) in data" :key="index">
        <b-carousel-slide 
        :caption="slide.title"
        :style="{ backgroundImage: 'url(' + require(`../../assets/${slide.image}`) + ')' }"
        >

        </b-carousel-slide>
        </a> -->
    </b-carousel>
</template>

<script>
    import carousel from "@/mock/projects"

    export default {
        name: 'Carousel',
        data() {
            return {
                data: carousel.slides
            };
        },
        methods: {
            carouselSlides() {
                return this.data.filter(n => {
                    return n.promoted
                });
            }
        }
    }
</script>