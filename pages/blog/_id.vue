<template>
    <div class="single-post">
        <!--start head-section-page -->
        <div class="head-section-page">

            <v-container>
                <v-row class="d-flex align-center">
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <img src="/pagesImages/services.svg">
                    </v-col>
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <h2>{{$t('blog')}}</h2>
                    </v-col>
                </v-row>
            </v-container>
            
        </div>



        <v-container>

            <div class="post">
                <div class="image">
                    <v-img
                        height="100%"
                        width="100%"
                        :src="`https://admin.crazyideaco.com/public/storage/`+row.image"
                    ></v-img>
                </div>
                <div dark class="content" v-if="$i18n.locale == 'ar'">
                    <h2> {{row.title_ar}} </h2>
                    <p v-html="row.description_ar"> </p>
                </div>

                <div class="content" v-if="$i18n.locale == 'en'">
                    <h2> {{row.title_en}} </h2>
                    <p v-html="row.description_en"> </p>
                </div>

                <div class="content" v-if="$i18n.locale == 'fr'">
                    <h2> {{row.title_fr}} </h2>
                    <p v-html="row.description_fr"> </p>
                </div>
                
            </div>


            

        </v-container>




    </div>
</template>

<script>
export default {
    head() {
        return {
            title: this.$t('blog')
        }
    },
    data: () => ({
        row: {},
    }),
    mounted() {
        this.fetchSomething();
    },
    methods: {
        async fetchSomething() {
            let url = process.env.moduleUrl + 'blogs/' + this.$route.params.id;
            this.$axios.$get(url).then((res) => {
                this.row = res.payload;
            })
        }
    }
}
</script>

<style>
.single-post .image {
    width: 100%;
    height: 550px;
}

.single-post h2 {
    font-size: 45px;
    line-height: 2;
    margin: 30px 0;
}

.single-post p {
    color: none !important;
}

</style>