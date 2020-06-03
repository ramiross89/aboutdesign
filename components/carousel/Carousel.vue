<template>
      <b-carousel
      id="carousel-fade"
      fade
      :interval="4000"
      controls
    >
      <!-- Text slides with image -->
        <router-link 
        :to="'/work/' + `${slide.url}`" 
        v-for="(slide, index) in carouselSlides()" 
        :key="index">
            <b-carousel-slide 
                :caption="slide.title"
                :style="{ backgroundImage: 'url(' + require(`../../assets/${slide.image}`) + ')' }">
            </b-carousel-slide>
        </router-link>
    </b-carousel>
</template>

<script>
    import json from "@/mock/projects";

    export default {
        name: 'Carousel',
        data() {
            return {
                data: json.projects
            };
        },
        methods: {
            carouselSlides() {
                return this.data.filter(n => {
                    return n.promoted
                });
            },
        }
    }
</script>