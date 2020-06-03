<template>
    <b-row class="showcase">
        <b-col 
        v-for="(item, index) in projectData.items" 
        :key="index"
        :class="{'col-md-12': item.full }"
        >
            <b-img
            :src=item.url
            fluid></b-img>
        </b-col>
    </b-row>
</template>

<script>
    export default {
        name: "Showcase",
        props: {
            projectData: { type:Object, required:true }
        },
    }
</script>
