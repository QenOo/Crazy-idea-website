<template>
    <v-card id="create">
        <v-speed-dial
            v-model="fab"
            :top="top"
            :bottom="bottom"
            :right="right"
            :left="left"
            :direction="direction"
            :open-on-hover="hover"
            :transition="transition"
        >
            <template v-slot:activator>
                <v-btn v-model="fab" color="blue darken-2" dark large fab>
                    <v-icon v-if="fab">
                        mdi-close
                    </v-icon>
                    <v-img v-else max-width="30px" src="/language.png"></v-img>
                </v-btn>
            </template>

            <v-btn @click.prevent.stop="changlang('ar')" fab icon large color="yellow">
                <v-img max-width="30px" src="/flagLang/egypt.svg"></v-img>
            </v-btn>

            <v-btn @click.prevent.stop="changlang('en')" fab icon large color="indigo">
                <v-img max-width="30px" src="/flagLang/en.svg"></v-img>
            </v-btn>

            <v-btn @click.prevent.stop="changlang('fr')" fab icon large color="blue">
                <v-img max-width="30px" src="/flagLang/france.svg"></v-img>
            </v-btn>

        </v-speed-dial>
    </v-card>
</template>

<script>
export default {

    data: () => ({
        direction: "top",
        fab: false,
        fling: false,
        hover: true,
        tabs: null,
        top: false,
        right: true,
        bottom: true,
        left: false,
        transition: "scale-transition",
    }),

    methods: {
        changlang (lang) {
            // Set lang in local
            this.$i18n.setLocale(lang);

            // Direction the website
            if ( lang == "ar") {
                this.$vuetify.rtl = true;
            } else {
                this.$vuetify.rtl = false;
            }

        }
    },
};
</script>

<style scoped>
.v-card {
    position: relative;
    right: -48px;
    bottom: -47px;
}
</style>
