<template>
    <div class="aboutus">
        <!--start head-section-page -->
        <div class="head-section-page">
            <v-container>
                <v-row class="d-flex align-center">
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <img src="/pagesImages/services.svg">
                    </v-col>
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <h2>{{$t('aboutUs')}}</h2>
                    </v-col>
                </v-row>
            </v-container>
            

        </div>
        <!--end head-section-page -->

        <v-container>
                    <div class="mttt">

                        <v-row v-for="item in this.res" :key="item.id" class="d-flex align-center d-xs-none">
                            <v-col cols="12" lg="6" md="6" sm="12" xm="12" class="vedoc">

                                <div class="vedo">
                                    <video poster="https://crazyideaco.com/wp-content/themes/crazy/images/crazy_poster.png" style="width: 100%;height: 100%;background: white;position:relative; border-radius: 50px 0 0 0;border:none;outline:none;z-index: 5;" autoplay="" muted="">
                                        <source src="https://crazyideaco.com/wp-content/themes/crazy/video/vid.mp4">
                                    </video>
                                </div>

                            </v-col>

                            <v-col cols="12" lg="6" md="6" sm="12" xm="12">




                                <div v-if="$i18n.locale == 'ar'" class="main-content about-company">

                                    <h5>
                                        {{item.title_ar}}
                                    </h5>

                                    <p>
                                        {{item.conent_ar}}
                                    </p>

                                </div>




                                <div v-if="$i18n.locale == 'en'" class="main-content about-company">

                                    <h5>
                                        {{item.title_en}}
                                    </h5>

                                    <p>
                                        {{item.conent_en}}
                                    </p>

                                </div>

                                <div v-if="$i18n.locale == 'fr'" class="main-content about-company">

                                    <h5>
                                        {{item.title_fr}}
                                    </h5>

                                    <p>
                                        {{item.conent_fr}}
                                    </p>

                                </div>


                                <div class="row">
                                    <v-btn class="my-2" large color="white blue--text" :href="`https://api.whatsapp.com/send?phone=2${item.contact_us}`" target="_blank"> {{$t('getStarted')}} </v-btn>
                                </div>

                            </v-col>
                        </v-row>

                    </div>
                </v-container>


    </div>
</template>

<script>
export default {
    head() {
        return {
            title: this.$t('aboutUs')
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
            let url = process.env.moduleUrl + 'about';
            const res = await this.$axios.$get(url);
            this.res = res.payload.data;
            console.log(this.res)
        }
    }
}
</script>

<style>


.main-content h4 {
    font-size: 35px;
    line-height: 1.5;
    text-shadow: 1px 1px 1px #ddd;

}

.main-content p {
    display: inline-block;
    margin-top: 30px;
    margin-bottom: 50px;
}



.mttt {
    margin-top: 50px;
}



.vedo {
    margin-top: 60px;
    height: 325px;
    width: 80%;
}

/* [lang="ar"] .vedo::before {
    top: -28px;
    left: -32px;
}

[lang="ar"] .vedo::after {
    bottom: -25px;
    right: -44px;
} */

.vedo #frme {
    width: 115%;
    height: 342px;
    border-radius: 35px 11px 29px 37px;
    margin-left: 6%;
    margin-top: 5%;
}


.vedo {
    position: relative;
}

.vedo iframe {
    position: relative;
    z-index: 2;
    background: #fff;
    border-radius: 100px 5px 5px 5px !important;
}

.vedo::before {
    content: '';
    position: absolute;
    top: -16px;
    left: -21px;
    width: 300px;
    height: 242px;
    border: 6px solid #00153F;
    z-index: 1;
    border-radius: 63px 0px 0px 0px;
}

.vedo::after {
    content: '';
    position: absolute;
    bottom: -33px;
    right: -29px;
    width: 241px;
    height: 170px;
    border: 5px solid #57FAEF;
    z-index: 1;
    border-radius: 0px 20px 0px 20px;
}

/* Extra small devices */

@media (max-width: 960px) {
    .mttt {
        margin: 0;
    }
    .vedo {
        margin: 20px 20px 0;
        height: 250px;
        width: 90%;
    }
    .main-content p {
        width: 80%;
        margin-top: 15px;
        font-size: 17px;
        margin-bottom: 30px;
    }
    .main-content h4 {
        font-size: 22px;
    }
}

@media (max-width: 300px) {
    .vedo,
    .vedoc {
        display: none;
    }
    .main-content p {
        width: 100% !important;
        margin-top: -1px;
        font-size: 15px;
        margin-bottom: 7px;
    }
}


.about-company h5 {
    color: #0861D4;
    font-size: 29px;
    margin-bottom: 21px;
    padding-top: 45px;
}


.row {
    margin: 0;
}
</style>