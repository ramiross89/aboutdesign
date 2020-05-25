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
      :key="index">
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
      :key="index">
        <b-col col lg="4">
            <p>{{feature.title}}</p>
          </b-col>
          <b-col col lg="4">
            <ul>
              <li 
              v-for="(item, index) in feature.list" 
              :key="index">{{item.title}}</li>
            </ul>
          </b-col>
          <b-col></b-col>
      </b-row>

      <b-row class="footer">
        <b-col col lg="4">
          <p class="h1">{{data.contact.title}}</p>
        </b-col>
        <b-col col lg="6">
          <ul>
            <li><a class="h1" :href="`mailto:${data.contact.email}`">{{data.contact.email}}</a></li>
            <li class="h1">{{data.contact.phone}}</li>
          </ul>
        </b-col>
        <b-col></b-col>
      </b-row>

      <div class="row footer">
        <b-col col lg="4">
          <p class="h1">{{data.social.title}}</p>
        </b-col>
        <b-col col lg="4">
          <ul>
            <li 
            v-for="(item, index) in data.social.list" 
            :key="index">
              <a 
              class="h1" 
              :href=item.href 
              target="_blank">{{item.title}}</a>
            </li>
          </ul>
        </b-col>
        <b-col></b-col>
      </div>

      <b-row class="footer deep">
        <b-col col lg="4">
          <p>© {{data.cc}}</p>
        </b-col>
        <b-col col lg="4">
          <p>{{data.state}},{{data.country}}<br>
           {{data.street}} {{data.homenum}}<br>
           {{data.recidence}}, {{data.zip}}</p>
        </b-col>
      </b-row>
    </b-container>
  </section>
</template>

<script>
  import about from "@/mock/about";

  export default {
    name: 'About',
    props: {
      toggleAbout: Boolean
    },
    data() {
        return {
            data: about
        };
    }
  }
</script>

