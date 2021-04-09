<template>
    <div class="services">
        <v-container>
            <v-row v-for="item in this.res" :key="item.id">

                <v-col v-if="$i18n.locale == 'ar'" lg="6" md="6" sm="12">

                    <h3 class="title heading--text">{{item.title_ar}}</h3>
                    <p>
                        {{item.description_ar}}
                    </p>

                    <v-btn class="myBtn" v-ripple="{ center: true }">
                        
                        test
                    </v-btn>

                </v-col>


                <v-col v-if="$i18n.locale == 'en'" lg="6" md="6" sm="12">

                    <h3 class="title heading--text">{{item.title_en}}</h3>
                    <p>
                        {{item.description_en}}
                    </p>

                </v-col>


                <v-col v-if="$i18n.locale == 'fr'" lg="6" md="6" sm="12">

                    <h3 class="title heading--text">{{item.title_fr}}</h3>
                    <p>
                        {{item.description_fr}}
                    </p>

                </v-col>

                <v-col lg="6" md="6" sm="12">
                    <v-img :src="'http://127.0.0.1:8000/storage/'+item.image" max-height="100%" max-width="100%"></v-img>
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
            const res = await this.$axios.$get('http://127.0.0.1:8000/api/module/services')
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
    font-size: 14px;
}

.myBtn {
    display: inline-block;
    width: 18%;
    height: 41px;
    border-radius: 8px;
    margin-right: 4%;
    margin-top: 15px;
    margin-bottom: 25px;
    background-image: linear-gradient(to right, #428EF3, #1542D3);
    color: #ffffff;
    font-family: semi;
    padding-top: 9px;
    font-size: 15px;
}
</style>