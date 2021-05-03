<template>
    <div class="blog">
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
        <!--end head-section-page -->



        <v-sheet class="mx-auto" max-width="1200" >
            <v-slide-group v-model="model" class="pa-4" center-active show-arrows >
                <v-slide-item v-for="item in this.res" :key="item.id">
                    <v-card
                        class="ma-4"
                        height="400"
                        width="400"
                    >

                        <v-img
                        height="250"
                        :src="$images(item.image)"
                        ></v-img>

                        <v-divider class="mx-4"></v-divider>

                        <v-card-title> {{item.title_ar}} </v-card-title>

                        <v-card-actions>
                        <v-btn
                            color="deep-purple lighten-2"
                            text
                            :to="`/blog/`+item.id"
                        >
                            {{$t('see')}}
                        </v-btn>
                        </v-card-actions>
                    </v-card>
                </v-slide-item>
            </v-slide-group>
        </v-sheet>



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
        model: null,
        res: [],
    }),
    mounted() {
        this.fetchSomething();
    },
    methods: {
        async fetchSomething() {
            let url = process.env.moduleUrl + 'blogs';
            let image = process.env.imageUrl;
            console.log(image)
            const res = await this.$axios.$get(url);
            this.res = res.payload.data;
        }
    }
}
</script>

<style>

</style>