<template>
    <div class="services">

        <!--start head-section-page -->
        <div class="head-section-page">
            <v-container>
                <v-row class="d-flex align-center">
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <img src="/pagesImages/services.svg">
                    </v-col>
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <h2>{{$t('services')}}</h2>
                    </v-col>
                </v-row>
            </v-container>

        </div>
        <!--end head-section-page -->

        <v-container>
            <v-row v-for="item in this.res" :key="item.id" class="d-flex align-center my-16">

                <v-col v-if="$i18n.locale == 'ar'" lg="6" md="6" sm="12" class="text-md-right text-center">

                    <h3 class="title heading--text">{{item.title_ar}}</h3>
                    <p>
                        {{item.description_ar}}
                    </p>

                    <v-btn class="myBtn" v-ripple="{ center: true }" large>
                        {{$t('orderNow')}}
                    </v-btn>

                </v-col>


                <v-col v-if="$i18n.locale == 'en'" lg="6" md="6" sm="12" class="text-md-left text-center">

                    <h3 class="title heading--text">{{item.title_en}}</h3>
                    <p>
                        {{item.description_en}}
                    </p>

                    <v-btn class="myBtn" v-ripple="{ center: true }" large>
                        {{$t('orderNow')}}
                    </v-btn>

                </v-col>


                <v-col v-if="$i18n.locale == 'fr'" lg="6" md="6" sm="12" class="text-md-left text-center">

                    <h3 class="title heading--text">{{item.title_fr}}</h3>
                    <p>
                        {{item.description_fr}}
                    </p>

                    <v-btn class="myBtn" v-ripple="{ center: true }" large>
                        {{$t('orderNow')}}
                    </v-btn>

                </v-col>

                <v-col lg="6" md="6" sm="12" class="d-flex justify-md-end justify-center">
                    <v-img :src="'http://127.0.0.1:8000/storage/'+item.image" max-height="100%" max-width="80%"></v-img>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
export default {
    head() {
        return {
            title: this.$t('services')
        }
    },
    data: () => ({
        res: [],
    }),
    mounted() {
        this.fetchSomething();
    },
    methods: {
        async fetchSomething() {
            let url = process.env.moduleUrl + 'services';
            const res = await this.$axios.$get(url);
            this.res = res.payload.data;
        }
    }
}
</script>

<style scoped>
.title {
    font-weight: bold;
    font-size: 36px !important;
    margin-bottom: 25px;
}

p {
    line-height: 1.6;
    display: inline-block;
    font-size: 18px !important;
}

.myBtn {
    background-image: linear-gradient(to right, #428EF3, #1542D3);
    color: #ffffff;
    padding-top: 9px;
    font-size: 15px;
}

/* @media (max-width: 960px) {
    .myBtn {
        display: block;
        margin: 0 auto;
    }
} */
</style>