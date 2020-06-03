<template>
    <b-container fluid>
        <div class="project">
            <b-row>
                <b-col>
                    <h1>{{project.title}} </h1>
                </b-col>
                <b-col>
                    <span>Services</span>
                    <ul>
                        <li v-for="(item, index) in project.services" :key="index">
                            {{item.name}},
                        </li>
                    </ul>
                </b-col>
            </b-row>

            <div class="featured-img">
                <b-img :src="require(`../../assets/${project.image}`)" fluid></b-img>
            </div>

            <b-row>
                <b-col lg="3">
                    <div>
                        <span>Industry</span>
                        {{project.type}}
                    </div>
                    <br />
                    <div>
                        <span>Collaborators</span>
                        {{project.collaborator}}
                    </div>
                </b-col>
                <b-col lg="3">
                    <span>Year</span>
                    {{project.year}}
                </b-col>
                <b-col>
                    <p class="description">{{project.description}}</p>
                </b-col>
            </b-row>
            
            <Showcase :projectData="projectData" />
        </div>

        <Footer />
    </b-container>
</template>

<script>
    import json from "@/mock/projects";
    import Footer from "@/components/footer/Footer.vue";
    import Showcase from "@/components/showcase/Showcase.vue";

    export default {
        name: "Project",
        props:{
            url: String,
        },
        components: {
            Footer,
            Showcase
        },
        data() {
            return {
                data: json.projects,
                project: null,
                projectData: null
            };
        },
        created() {
            this.projectFiltered();
        },
        computed: {

        },
        methods: {
            projectFiltered() {
                console.log(this.url)
                this.project =  this.data.find(n => n.url === this.url);
                this.projectData = this.project.showcase;
                return this.project;
            }
        }
    }
</script>