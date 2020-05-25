<template>
  <footer>
    <b-row>
        <b-col class="cc"><span>© {{data.cc}}</span></b-col>

        <b-col class="location">
            <div>
                {{data.state}}, {{data.country}} <br>
                {{data.street}} {{data.homenum}}<br>
                {{data.recidence}}, {{data.zip}}
            </div>
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
