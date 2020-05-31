<template>
  <section id="about" :class="{active: toggleAbout}">
    <b-container fluid>
      <div class="intro">
        <h1>{{data.body}}</h1>

        <b-row class="sub">
          <b-col col lg="3" class="h1">
            <p>{{data.services.title}}</p>
          </b-col>
          <b-col col lg="1"></b-col>
          <b-col col lg="4">
            <p>{{data.services.body}}</p>
            <br>
          </b-col>
        </b-row>
      </div>

      <b-row 
      v-for="(feature, index) in data.services.features" 
      :key="feature.title + index">
        <b-col></b-col>
        <b-col col lg="4">
          <p>
            {{feature.title}}<br>
            <i>{{feature.subtitle}} </i>
          </p>
        </b-col>
        <b-col col lg="4">
          <p>{{feature.body}}</p>
          <ul>
            <li 
            v-for="(item, index) in feature.list" 
            :key="index"
            >{{item.title}}</li>
          </ul>
        </b-col>
      </b-row>

      <b-row class="featured" 
      v-for="(feature, index) in data.features" 
      :key="feature.title + index">
        <b-col col lg="4">
            <p>{{feature.title}}</p>
          </b-col>
          <b-col col lg="4">
            <ul>
              <li 
              v-for="(item, index) in feature.list" 
              :key="item.title + index">{{item.title}}</li>
            </ul>
          </b-col>
          <b-col></b-col>
      </b-row>
      
      <Footer />
    </b-container>
  </section>
</template>

<script>
  import about from "@/mock/about";
  import Footer from "@/components/footer/Footer";

  export default {
    name: 'About',
    props: {
      toggleAbout: Boolean
    },
    components: {
        Footer
    },
    data() {
        return {
            data: about
        };
    }
  }
</script>

