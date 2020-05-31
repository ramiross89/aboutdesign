<template>
    <div>
        <header>
            <b-container fluid>
                <b-row>
                    <b-col>
                        <router-link to="/" @click.native="closeAbout">
                            <img class="logo" alt="logo" src="../../assets/logo_w.svg">
                        </router-link> 
                    </b-col>
                    <b-col md="3" offset-md="3" class="links">
                        <!-- <router-link @click.native="closeAbout" to="/work">Work</router-link>  -->
                        <router-link class="link" to="/work">Work</router-link> 

                        <router-link class="link" to="/about">Information</router-link> 

                        <!-- <div
                        :class="['link', {active: showAbout}]"
                        @click="showAbout = !showAbout">
                          Information
                        </div> -->
                        <!-- <div class="plus">
                            <div class="x"
                            :class="{active: showAbout}"
                            @click="showAbout = !showAbout">
                                <img src="../../assets/cruz_w.svg" alt="">
                            </div>
                        </div> -->
                    </b-col>
                </b-row>
            </b-container> 
        </header>
        
        <!-- <transition name="fade">
            <About v-if="showAbout"/>
        </transition> -->
    </div>
</template>

<script>
    import About from "@/views/about/About"

    export default {
        name: "NavBar",
        components: {
            About
        },
        data() {
            return {
                showAbout: false
            }
        },
        methods: {
            // close about if click other links instead of 'info' link
            closeAbout(){
                if (this.showAbout) {
                    this.showAbout = false;
                }
            }
        }
    }
</script>
