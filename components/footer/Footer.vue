<template>
    <footer>
        <b-row>
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

        <b-row>
            <b-col col lg="4">
                <p class="h1">{{data.social.title}}</p>
            </b-col>
            <b-col col lg="4">
                <ul>
                    <li 
                    v-for="(item, index) in data.social.list" 
                    :key="item.title + index">
                        <a 
                        class="h1" 
                        :href=item.href 
                        target="_blank">{{item.title}}</a>
                    </li>
                </ul>
            </b-col>
            <b-col></b-col>
        </b-row>

        <b-row class="deep">
            <b-col class="cc">
                <p>© {{data.cc}}</p>
            </b-col>
            <b-col class="location">
                <p>{{data.state}},{{data.country}}<br>
                {{data.street}} {{data.homenum}}<br>
                {{data.recidence}}, {{data.zip}}</p>
            </b-col>
        </b-row>
    </footer>
</template>

<script>
    import about from "@/mock/about";

    export default {
        name: "Footer",
        data() {
            return {
                data: about
            };
        }
    }
</script>
