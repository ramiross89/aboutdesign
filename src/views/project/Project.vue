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

            <b-row class="showcase">
                <b-col 
                v-for="(item, index) in project.gallery" 
                :key="index"
                md="6">
                    <b-img
                    :src=item.image
                    fluid></b-img>
                </b-col>
            </b-row>
        </div>

        <Footer />
    </b-container>
</template>

<script>
    import json from "@/mock/projects";
    import Footer from "@/components/footer/Footer";

    export default {
        name: "Project",
        props: ['url'],
        components: {
            Footer
        },
        data() {
            return {
                data: json.projects,
                project: null,
            };
        },
        created() {
            this.projectFiltered();
        },
        methods: {
            projectFiltered() {
                this.project =  this.data.find(n => n.url === this.url);
                return this.project;
            }
        }
    }
</script>