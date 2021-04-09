<template>
    <div class="services">
        <v-container>
            <v-row v-for="item in this.res" :key="item.id">

                <v-col v-if="$i18n.locale == 'ar'" lg="6" md="6" sm="12">

                    <h3 class="title">{{item.title_ar}}</h3>
                    <p>
                        {{item.description_ar}}
                    </p>

                </v-col>


                <v-col v-if="$i18n.locale == 'en'" lg="6" md="6" sm="12">

                    <h3 class="title">{{item.title_en}}</h3>
                    <p>
                        {{item.description_en}}
                    </p>

                </v-col>


                <v-col v-if="$i18n.locale == 'fr'" lg="6" md="6" sm="12">

                    <h3 class="title">{{item.title_fr}}</h3>
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
            console.log(this.lang)
        }
    }
}
</script>

<style scoped>
.title {
    font-weight: bold;
    font-size: 46px;
    margin-bottom: 25px;
}
</style>