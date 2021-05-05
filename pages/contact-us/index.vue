<template>
    <div class="contact-us">
        <!--start head-section-page -->
        <div class="head-section-page">

            <v-container>
                <v-row class="d-flex align-center">
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <img src="/pagesImages/services.svg">
                    </v-col>
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <h2>{{$t('contactUs')}}</h2>
                    </v-col>
                </v-row>
            </v-container>
            

        </div>
        <!--end head-section-page -->









        <div class="contact mt-5">
            <v-container>
                <v-row>

                    <v-col cols="12" md="5" class="cont-info mt-5">
                        <h6 class="headingtow--text">{{$t('getInTouch')}}</h6>
                        <h2 class="heading--text">{{$t('letsTalk')}}</h2>
                        <p class="heading--text">
                            {{$t('pragContact')}}
                        </p>

                        <div>
                            <div class="row">
                                <span class="">
                                    <a href="#" class="social1 text-center">
                                        <svg class="svg-inline--fa fa-facebook-f fa-w-9" aria-hidden="true" data-prefix="fab" data-icon="facebook-f" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 264 512" data-fa-i2svg=""><path fill="currentColor" d="M76.7 512V283H0v-91h76.7v-71.7C76.7 42.4 124.3 0 193.8 0c33.3 0 61.9 2.5 70.2 3.6V85h-48.2c-37.8 0-45.1 18-45.1 44.3V192H256l-11.7 91h-73.6v229"></path></svg><!-- <i class="fab fa-facebook-f"></i> -->
                                    </a>
                                </span>
                                <span class="">
                                    <a href="#" class="text-center">
                                        <svg class="svg-inline--fa fa-instagram fa-w-14" aria-hidden="true" data-prefix="fab" data-icon="instagram" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" data-fa-i2svg=""><path fill="currentColor" d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"></path></svg><!-- <i class="fab fa-instagram"></i> -->
                                    </a>
                                </span>

                                <span class="">
                                    <a href="#" class="text-center">
                                        <svg class="svg-inline--fa fa-youtube fa-w-18" aria-hidden="true" data-prefix="fab" data-icon="youtube" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512" data-fa-i2svg=""><path fill="currentColor" d="M549.655 124.083c-6.281-23.65-24.787-42.276-48.284-48.597C458.781 64 288 64 288 64S117.22 64 74.629 75.486c-23.497 6.322-42.003 24.947-48.284 48.597-11.412 42.867-11.412 132.305-11.412 132.305s0 89.438 11.412 132.305c6.281 23.65 24.787 41.5 48.284 47.821C117.22 448 288 448 288 448s170.78 0 213.371-11.486c23.497-6.321 42.003-24.171 48.284-47.821 11.412-42.867 11.412-132.305 11.412-132.305s0-89.438-11.412-132.305zm-317.51 213.508V175.185l142.739 81.205-142.739 81.201z"></path></svg><!-- <i class="fab fa-youtube"></i> -->
                                    </a>
                                </span>

                                <span>
                                    <a href="#" class="text-center">
                                        <svg class="svg-inline--fa fa-behance fa-w-18" aria-hidden="true" data-prefix="fab" data-icon="behance" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512" data-fa-i2svg=""><path fill="currentColor" d="M232 237.2c31.8-15.2 48.4-38.2 48.4-74 0-70.6-52.6-87.8-113.3-87.8H0v354.4h171.8c64.4 0 124.9-30.9 124.9-102.9 0-44.5-21.1-77.4-64.7-89.7zM77.9 135.9H151c28.1 0 53.4 7.9 53.4 40.5 0 30.1-19.7 42.2-47.5 42.2h-79v-82.7zm83.3 233.7H77.9V272h84.9c34.3 0 56 14.3 56 50.6 0 35.8-25.9 47-57.6 47zm358.5-240.7H376V94h143.7v34.9zM576 305.2c0-75.9-44.4-139.2-124.9-139.2-78.2 0-131.3 58.8-131.3 135.8 0 79.9 50.3 134.7 131.3 134.7 61.3 0 101-27.6 120.1-86.3H509c-6.7 21.9-34.3 33.5-55.7 33.5-41.3 0-63-24.2-63-65.3h185.1c.3-4.2.6-8.7.6-13.2zM390.4 274c2.3-33.7 24.7-54.8 58.5-54.8 35.4 0 53.2 20.8 56.2 54.8H390.4z"></path></svg><!-- <i class="fab fa-behance"></i> -->
                                    </a>
                                </span>

                            </div>

                        </div>

                        <h5 class="heading--text">
                            <span class="textinfo--text">
                                {{$t('howers')}} 
                            </span>
                            {{$t('hoursWork')}}
                        </h5>

                        <a href="#" id="cnn">SomeOne@gmail.com</a>

                        <a href="#" id="cnn">Call : +20102547898</a>

                    </v-col>

                    <v-col cols="12" md="7">
                        <v-form v-model="valid" ref="form">

                            <v-container>
                                <v-row>

                                    <v-col cols="12" md="6">
                                        <v-text-field
                                            v-model="name"
                                            :rules="nameRules"
                                            :counter="15"
                                            :label="$t('fullName')"
                                            required
                                        ></v-text-field>
                                    </v-col>


                                    <v-col cols="12" md="6"> 
                                        <v-select
                                            v-model="select"
                                            :items="items"
                                            :rules="[v => !!v || this.$t('serviceIsRequired')]"
                                            :label="$t('selectService')"
                                            required
                                        ></v-select>
                                    </v-col>


                                    <v-col cols="12" md="6">
                                        <v-text-field
                                            v-model="email"
                                            :rules="emailRules"
                                            :label="$t('email')"
                                            required
                                        ></v-text-field>
                                    </v-col>


                                    <v-col cols="12" md="6">
                                        <v-text-field
                                            v-model="mobile"
                                            :rules="mobileRules"
                                            :label="$t('mobile')"
                                            required
                                        ></v-text-field>
                                    </v-col>



                                    <v-col cols="12">
                                        <v-textarea
                                            counter
                                            clearable
                                            :label="$t('message')"
                                            :placeholder="$t('helpYourProject')"
                                            v-model="message"
                                        ></v-textarea>
                                    </v-col>



                                    <v-col cols="12"> 
                                        <v-checkbox
                                            v-model="checkbox"
                                            :rules="[v => !!v || this.$t('agreeToContinue')]"
                                            :label="$t('understandPrivacyPolicy')"
                                            required
                                        ></v-checkbox>
                                    </v-col>

                                    <v-col cols="12">
                                        
                                        <v-btn
                                            :disabled="!valid"
                                            color="success"
                                            @click.prevent="contact"
                                            >
                                            {{$t('contactUs')}}
                                        </v-btn>
                                        
                                    </v-col>

                                </v-row>
                            </v-container>


                            <!-- success alert -->
                            <div class="text-center">

                                <v-snackbar v-model="snackbar" :timeout="timeout" centered top elevation="24" >
                                    <h3 class="text-center">
                                        <span class="light-green--text accent-3 ">
                                            {{ $t('welcome') }}
                                        </span>
                                        <h2 class="white--text font-bolder py-4">
                                            {{this.value1}}
                                        </h2>
                                        <span class="light-green--text  accent-3">
                                            {{ $t('snackbar') }}
                                        </span>
                                    </h3>

                                    <template>
                                        <v-btn color="error" text @click.prevent="resetValidation" class="mx-auto d-block" > {{$t('close')}} </v-btn>
                                    </template>
                                </v-snackbar>
                                
                            </div>
                            <!-- success alert -->


                            <!-- un success alert -->
                            <div class="text-center">

                                <v-snackbar v-model="snackbart" :timeout="timeout" >
                                
                                    <div class="error--text">
                                        <h3>{{ $t('snackbart') }}</h3>
                                    </div>
                                    <template>
                                        <v-btn color="danger" text @click="snackbart = false" > {{$t('close')}} </v-btn>
                                    </template>

                                </v-snackbar>
                                
                            </div>
                            <!-- un success alert -->
                        </v-form>
                    </v-col>



                </v-row>
            </v-container>
        </div>








    </div>
</template>

<script>
export default {
    head() {
        return {
            title: this.$t('contactUs')
        }
    },
    data() {
        return {
            name:'',
            select: '',
            email:'',
            mobile:'',
            message:'',
            value1: '',
            response:[],
            errors:{},
            valid: false,
            checkbox: false,
            snackbar: false,
            snackbart: false,
            timeout: 10000,
            items: [
                'Web Application',
                'Mobile Application',
                'Digital Marketing',
                'Motion Graphic',
                'Branding',
                'SEO',
            ],
            nameRules: [
                v => !!v || this.$t('nameIsRequired'),
                v => v.length <= 15 || this.$t('NameCharacters'),
            ],
            emailRules: [
                v => !!v || this.$t('mailIsRequired'),
                v => /.+@.+/.test(v) || this.$t('mailMustBeValid'),
            ],
            mobileRules: [
                v => !!v || this.$t('mobileIsRequired'),
                v => /^[0-9]+$/.test(v) || this.$t('mobileNotCharacters'),
                v => v.length >= 11 || this.$t('mobileCharacters'),
            ],
        }
    },
    mounted() {

    },
    methods: {
        contact() {
            let url = 'https://admin.crazyideaco.com/public/api/contacts';
            let data = {
                name: this.name,
                company_name: this.select,
                email_address: this.email,
                phone_number: this.mobile,
                message: this.message
            }
            this.$axios.post(url , data).then((res) => {
                this.response = res;
                console.log(this.response)
                if(this.response.status == 200){
                    this.snackbar = true
                    this.value1 = this.name;
                    this.errors= {};
                } else {
                    this.snackbart = true
                    this.errors = res.data.payload;
                }
            });
        },
        resetValidation () {
            this.name = '';
            this.select = '',
            this.email = '',
            this.mobile = '',
            this.message = '',
            this.$refs.form.resetValidation()
            this.snackbar = false
        },
    }
}
</script>

<style>
/*start contact us page*/
.cont-info h6 {
    font-size: 16px;
    margin-bottom: 10px;
}

.cont-info h2 {
    margin-bottom: 25px;
    margin-bottom: 11px;
    font-size: 36px;
}

.cont-info p {
    font-size: 15px;
    margin-bottom: 35px;
}

.cont-info span a {
    font-size: 18px;
}

.cont-info span a {
    margin-right: 25px;
    margin-left: 6px;
}

[lang="ar"] .cont-info span a {
    margin-left: 25px;
    margin-right: 6px;
}

.cont-info span a svg {
    width: 23px;
    height: 23px;
}

.cont-info h5 {
    color: #00153F;
    font-size: 15px;
    margin-top: 22px;

}

.cont-info #cnn {
    display: block;
    font-size: #428EF3;
    margin-top: 15px;
    margin-bottom: 12px;
}

/* .cont-det .inp label {
    color: #00153F;
    font-family: pop-reg;
    font-size: 16px;
    margin-left: 5%;
}

.cont-det .inp input {
    border-right: 0px solid #ffffff !important;
    border-left: 0px solid #ffffff !important;
    border-top: 0px solid #ffffff !important;
    width: 80%;
    margin-left: 4%;

} */

.cont-det .rww1 {
    margin-top: 55px;
}

/*end contact us page*/


</style>