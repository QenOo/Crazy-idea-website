<template>
    <div class="projects">
        <!--start head-section-page -->
        <div class="head-section-page">
            <v-container>
                <v-row class="d-flex align-center">
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <img src="/pagesImages/services.svg">
                    </v-col>
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <h2>{{$t('projects')}}</h2>
                    </v-col>
                </v-row>
            </v-container>

        </div>
        <!--end head-section-page -->



        <div class="heading-section text-center my-16">
            <div class="textinfo--text"> <span>|</span> {{$t('interdouceOurProjects')}} </div>
            <h4> {{$t('growYourBusiness')}} </h4>
        </div>






        <div class="grow wow animate__ animate__tada animated" style="visibility: visible; animation-name: tada;">
            <div class="container">

                <div class="row">

                    <div class="col-md-4 col-12">

                        <div class="intro-project text-center">

                            <img src="/projects/rain.svg">
                            <h5>Daftr Accouting System</h5>
                            <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
                                invidunt ut labore et dolore magna
                            </p>


                        </div>


                        <div class="intro-project text-center">

                            <img src="/projects/rain.svg">
                            <h5>Daftr Accouting System</h5>
                            <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
                                invidunt ut labore et dolore magna
                            </p>

                        </div>

                    </div>

                    <div class="col-md-4 col-12 text-center">
                        <img src="/projects/grow.svg" id="grow-img">

                    </div>

                    <div class="col-md-4 col-12">

                        <div class="intro-project text-center">

                            <img src="/projects/rain.svg">
                            <h5>Daftr Accouting System</h5>
                            <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
                                invidunt ut labore et dolore magna
                            </p>

                        </div>


                        <div class="intro-project text-center">

                            <img src="/projects/rain.svg">
                            <h5>Daftr Accouting System</h5>
                            <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
                                invidunt ut labore et dolore magna
                            </p>

                        </div>

                    </div>

                </div>
            </div>
        </div>




        <v-container class="projects-item">
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
                    <v-img :src="'https://admin.crazyideaco.com/public/storage/'+item.image" max-height="100%" max-width="80%"></v-img>
                </v-col>
            </v-row>
        </v-container>


    </div>
</template>

<script>
export default {
    head() {
        return {
            title: this.$t('projects')
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
            let url = process.env.moduleUrl + 'projects';
            const res = await this.$axios.$get(url);
            this.res = res.payload.data;
        }
    }
}
</script>

<style scoped>
.projects-item .title {
    font-weight: bold;
    font-size: 36px !important;
    margin-bottom: 25px;
}

.projects-item p {
    line-height: 1.6;
    display: inline-block;
    font-size: 18px !important;
}

.projects-item .myBtn {
    background-image: linear-gradient(to right, #428EF3, #1542D3);
    color: #ffffff;
    font-size: 15px;
}


.heading-section h4 {
    font-size: 30px;
}

/*start grow*/
.grow {
    padding-top: 50px;
    min-height: 600px;
    margin-bottom: 45px;
}

.grow h4 {
    margin-top: 25px;
    line-height: 1.8;
    font-size: 25px;
    display: inline-block;
    margin-left: 25px;
}


.grow #grow-img1 {
    margin-top: -100px;
    width: 25px !important;
    height: 25px !important;
    animation-name: grow;
    animation-duration: 2s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    animation-timing-function: ease-in-out;

}

.grow .intro-project {
    height: 45%;
    margin-bottom: 1%;
    margin-top: 30px;
}

.grow .intro-project img {
    width: 55px;
    height: 55px;
    border: 1px solid;
    border-radius: 50%;
    padding: 5px;
}

.grow .intro-project p {
    display: inline-block;
    width: 80%;
    text-align: center;
    font-size: 12.5px;
    margin-bottom: 12px;

}

.grow #grow-img {
    width: 80%;
    height: 100%;

}

.grow .intro-project h5 {
    margin-top: 21px;
    margin-bottom: 10px;
    font-size: 17px;
}

/*end grow*/
</style>