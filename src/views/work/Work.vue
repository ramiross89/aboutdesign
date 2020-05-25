<template>
    <b-container class="work" fluid>
        <b-row>
            <b-col 
            v-for="(slide, index) in data" 
            :key="index"
            md="6">
                <b-img
                :src="require(`../../assets/${slide.image}`)"
                :alt=slide.title
                fluid></b-img>
                <div class="label">
                    {{slide.title}} / {{slide.type}} / {{slide.year}}
                </div>
            </b-col>
        </b-row>

        <Footer />
    </b-container>
</template>

<script>
    import carousel from "@/mock/projects";
    import Footer from "@/components/footer/Footer"

    export default {
        name: "Work",
        components: {
            Footer
        },
        data() {
            return {
                data: carousel.slides
            };
        }
    }
</script>