<template>
    <!--start main-footer-->
    <div class="main-footer">
        <v-container>
            <!--start foter-->
            <div class="foter">
                <v-row class="d-flex align-center">
                    <v-col cols="12" lg="3" md="6" sm="6" xs="12">
                        <img src="/logow.svg">
                    </v-col>
                    <v-col cols="12" lg="3" md="6" sm="6" xs="12">
                        <h4>{{$t('usefulLinks')}}</h4>
                        <ul v-for="item in menuItems" :key="item.index">
                            <li>
                                <nuxt-link :to="item.path">{{ $t(`${item.title}`)  }}</nuxt-link>
                            </li>
                        </ul>
                    </v-col>
                    <v-col cols="12" lg="3" md="6" sm="6" xs="12">
                        <h4>{{$t('information')}}</h4>
                        <ul>
                            <li><a href="#">{{$t('helpSupport')}}</a></li>
                            <li><a href="#">{{$t('pravicyPolicy')}}</a></li>
                            <li><a href="#">{{$t('pricing')}}</a></li>
                            <li><a href="#">{{$t('terms')}}</a></li>
                            <li><a href="#">{{$t('condition')}}</a></li>
                        </ul>
                    </v-col>
                    <v-col cols="12" lg="3" md="6" sm="6" xs="12">
                        <h4>{{$t('contacts')}}</h4>
                        <ul>
                            <li><a href="#">Someone@Gmail.Com</a></li>
                            <li><a href="#">+2055254545155</a></li>
                            <li><a href="#">555452550220</a></li>
                            <li><a href="#">Egypt,Mansoura 26 El-Magzer ST.</a></li>
                            <li><a href="#">Egypt,Mansoura 26 El-Magzer ST.</a></li>
                        </ul>
                    </v-col>

                </v-row>
            </div>
            <!--end foter-->

            <footer class="d-flex justify-space-between">
                
                <h5>{{$t('allRights')}}</h5>
                <div class="crazy">
                    <h6>Made with <img src="/red.svg"> by Crazy Idea</h6>
                    <p class="text-right">{{$t('thinkOut')}}</p>
                </div>
            </footer>
        </v-container>
    </div>
    <!--end main footer-->
</template>

<script>
export default {
    data() {
        return {
            drawer: false,
            group: null,
            menuItems: [
                {title: 'services', path: 'services', icon: 'mdi-face-agent'},
                {title: 'projects', path: 'projects', icon: 'mdi-account-group'},
                {title: 'works', path: 'works', icon: 'mdi-briefcase'},
                {title: 'blog', path: 'blog', icon: 'mdi-shield-account'},
                {title: 'contactUs', path: 'contact-us', icon: 'mdi-shield-account'},
            ]
        };
    }
}
</script>

<style>
/*start main-footer*/
.main-footer {
    background-image: url('/footer.svg');
    background-repeat: no-repeat;
    background-size: cover;
    padding-top: 20%;


}

.main-footer .foter {
    margin-top: 80px;
    border-bottom: .5px solid rgba(255, 255, 255, 0.411);
    padding-bottom: 50px;
}

.main-footer .foter img {
    width: 60%;
    height: 120px;
}

.main-footer .foter ul {
    padding-left: 0px;
}

.main-footer .foter h4 {
    color: #ffffff;
    font-size: 26px;
    margin-bottom: 21px;
}

.main-footer .foter ul li,
.main-footer .foter ul li a {
    margin-top: 10px;
    margin-bottom: 10px;
    color: #ffffff;
    font-size: 18px;
    margin-left: 3px;
    text-decoration: none;
}


.main-footer .foter p {
    display: inline-block;
    color: #ffffff !important;
    font-size: 18px;
    margin-top: 10px;
    margin-bottom: 10px;
}


footer {
    padding-top: 22px;
    padding-bottom: 22px;
}

footer h5 {
    color: #ffffff;
    font-size: 16px;
    margin-top: 15px;
}

footer .crazy {
    text-align: center;
}

footer .crazy h6 {
    color: #ffffff;
    font-size: 18px;
}


footer .crazy p {
    color: #ffffff;
    text-align: center;
    display: inline;
}

/*end main-footer*/

</style>