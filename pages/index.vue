<template>
    <div class="home">
        
        <div class="container-parallax">
            <ul class="scene" id="scene">
                <li class="layer" data-depth="0.5"><img src="/header/rocket.png"></li>
                <li class="layer tow" data-depth="0.8"><img src="/header/Grouptt.svg"></li>
                <li class="layer three" data-depth="-0.7"><img src="/header/Groupthr.svg"></li>
                <li class="layer one" data-depth="-0.7"><img src="/header/zohal.svg"></li>
                <li class="layer" data-depth="-0.3"><img src="/header/planet1.png"></li>
                <li class="layer three" data-depth="-0.7"><img src="/header/Groupthr.svg"></li>
            </ul>
            <div class="overlay-head">
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

                                <div v-if="$i18n.locale == 'ar'" class="main-content">


                                    <p id="small">| {{item.title_ar}} </p>
                                    <h4>
                                        {{item.heading_ar}}
                                    </h4>

                                    <p>{{item.description_ar}}</p>

                                </div>

                                <div v-if="$i18n.locale == 'en'" class="main-content">


                                    <p id="small">| {{item.title_en}} </p>
                                    <h4>
                                        {{item.heading_en}}
                                    </h4>

                                    <p>{{item.description_en}}</p>

                                </div>

                                <div v-if="$i18n.locale == 'fr'" class="main-content">


                                    <p id="small">| {{item.title_fr}} </p>
                                    <h4>
                                        {{item.heading_fr}}
                                    </h4>

                                    <p>{{item.description_fr}}</p>


                                </div>


                                <div class="row">
                                    <v-btn class="my-2" large color="white blue--text" :href="`https://api.whatsapp.com/send?phone=2${item.contact_us}`" target="_blank"> {{$t('getStarted')}} </v-btn>
                                    <v-btn large class="mx-2 my-2" outlined color="white" :href="item.download" target="_blank">
                                        {{$t('downloadPortofilio')}}
                                    </v-btn>
                                </div>

                            </v-col>
                        </v-row>

                    </div>
                </v-container>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'home',
    data: () => ({
        res: []
    }),
    head() {
        return {
            title: this.$t('home')
        }
    },
    mounted() {
        this.fetchSomething();
        var scene = document.getElementById('scene');
        var parallax = new Parallax(scene);
    },
    methods: {
        async fetchSomething() {
            let url = process.env.moduleUrl + 'slider';
            const res = await this.$axios.$get(url);
            this.res = res.payload.data;
        }
    }
};
</script>


<style scoped>
.home {
    height: 3000px;
}
.scene {
    position: relative;
}

.scene .tow {
    position: absolute;
    top: 50%;
    right: 50%;
    margin-top: 260px;
}

.scene .one {
    position: absolute;
    width: 200px;
    height: 200px;
    margin-top: 130px;
    top: 100%;
    right: 70%;
}

.scene .three img {
    padding: 100px 200px;
}
.container-parallax
{
	width: 100%;
	min-height: 100vh;
	max-height: 100vh;
	height: 100vh;
	overflow: hidden;
	background: url('/header/bkCover.svg');
    background-position: bottom;
    background-size: cover;
    position: relative;
    display: block;
}
.overlay-head {
    background: rgba( 255, 255, 255, 0.00 );
    box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    backdrop-filter: blur( 2.0px );
    -webkit-backdrop-filter: blur( 4.0px );
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

.main-content h4 {
    font-weight: bolder;
    color: #ffffff;
    font-size: 35px;
    line-height: 1.5;
    text-shadow: 1px 1px 1px #ddd;

}

.main-content p {
    color: #ffffff;
    display: inline-block;
    width: 88%;
    margin-top: 30px;
    font-size: 19px;
    margin-bottom: 50px;
    text-shadow: 1px 1px 1px rgb(146, 146, 146);
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

.row {
    margin: 0;
}

</style>