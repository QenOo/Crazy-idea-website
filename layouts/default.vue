<template>
    <v-app dark >
        <!-- ?== My Navbar -->
        <app-navbar />
        <!-- ?== My Navbar -->

        <!-- ?==  content -->
        <v-main>
            <v-container>
                <nuxt />
            </v-container>
        </v-main>
        <!-- ?==  content -->

        <!-- ?== my content -->
        <v-footer app>
            <span>&copy; {{ new Date().getFullYear() }}</span>
        </v-footer>
        <!-- ?== my content -->

        <!-- ?== App Setting -->
        <app-setting />
        <!-- ?== App Setting -->
    </v-app>
</template>

<script>
import appSetting from "../components/app-setting.vue";
import Vuetify from 'vuetify'
import colors from 'vuetify/es5/util/colors'


export default {
    components: { appSetting },
    data() {
        return {};
    },
    head() {
        return {
            titleTemplate: this.$t("websiteName") + " => %s",
            title: "Crazy Idea",
            htmlAttrs: {
                lang: this.$i18n.locale
            }
        };
    },
    mounted() {

        if ( this.$i18n.locale == "ar") {
            this.$vuetify.rtl = true;
        } else {
            this.$vuetify.rtl = false;
        }


        // toggle dark mode
        const theme = localStorage.getItem("dark_theme");
        this.$vuetify.theme.themes.light.heading = '#00153F'
        if (theme) {
            if (theme == "true") {
                this.$vuetify.theme.dark = true;
            } else {
                this.$vuetify.theme.dark = false;
                this.$meta().refresh()
            }
        }
    },
    vuetify: new Vuetify({
        theme: {
            dark: true,
            themes: {
                dark: {
                heading: '#fff',
                accent: colors.grey.darken3,
                secondary: colors.amber.darken3,
                info: colors.teal.lighten1,
                warning: colors.amber.base,
                error: colors.deepOrange.accent4,
                success: colors.green.accent3
                },
                light: {
                heading: '#00153F',
                secondary: colors.grey.darken1,
                accent: colors.shades.black,
                error: colors.red.accent3,
                background: colors.indigo.lighten5
                },
            }
        }
    })
};
</script>


<style>
/* * {
    transition: all ease-in-out .2s;
} */

body  {
    font-family: 'Tajawal', sans-serif !important;
}

[lang="ar"] .v-application {
    font-family: 'Tajawal', sans-serif !important;
}
</style>