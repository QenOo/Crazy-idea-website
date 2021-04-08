<template>
    <v-app dark>
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
        if (theme) {
            if (theme == "true") {
                this.$vuetify.theme.dark = true;
            } else {
                this.$vuetify.theme.dark = false;
            }
        }
    }
};
</script>


<style>
.toggle {
  --size: 2rem;
  -webkit-appearance: none;
     -moz-appearance: none;
          appearance: none;
  outline: none;
  cursor: pointer;
  width: var(--size);
  height: var(--size);
  box-shadow: inset calc(var(--size) * 0.33) calc(var(--size) * -0.25) 0;
  border-radius: 999px;
  color: #e6e6ff;
  transition: all 500ms;
}
.toggle:checked {
  --ray-size: calc(var(--size) * -0.4);
  --offset-orthogonal: calc(var(--size) * 0.65);
  --offset-diagonal: calc(var(--size) * 0.45);
  transform: scale(0.75);
  color: #ffaa00;
  box-shadow: inset 0 0 0 var(--size), calc(var(--offset-orthogonal) * -1) 0 0 var(--ray-size), var(--offset-orthogonal) 0 0 var(--ray-size), 0 calc(var(--offset-orthogonal) * -1) 0 var(--ray-size), 0 var(--offset-orthogonal) 0 var(--ray-size), calc(var(--offset-diagonal) * -1) calc(var(--offset-diagonal) * -1) 0 var(--ray-size), var(--offset-diagonal) var(--offset-diagonal) 0 var(--ray-size), calc(var(--offset-diagonal) * -1) var(--offset-diagonal) 0 var(--ray-size), var(--offset-diagonal) calc(var(--offset-diagonal) * -1) 0 var(--ray-size);
}

.toggle {
  z-index: 1;
}
</style>