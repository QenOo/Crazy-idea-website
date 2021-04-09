<template>
    <v-card class="appSetting" >
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
                <v-btn v-model="fab" color="blue darken-1" dark large fab>
                    <v-icon v-if="fab">
                        mdi-close
                    </v-icon>
                    <v-img v-else max-width="30px" src="/language.png"></v-img>
                </v-btn>
            </template>

            <v-btn @click.stop="toggle_dark_mode" fab dark large icon color="yellow" >
                
                <input :class="{ checked: checked }" class="toggle btn-dark-mod" type="checkbox">
                
            </v-btn>

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
        checked: false
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

        },
        toggle_dark_mode () {
            this.checked = !this.checked
            this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
            localStorage.setItem("dark_theme", this.$vuetify.theme.dark.toString());
        }
    },
};
</script>

<style scoped>
.appSetting {
    position: fixed;
    bottom: 20px;
    right: 20px;
}
.appSetting .v-speed-dial {
    position: absolute;
    bottom: 50px;
}

.appSetting .v-btn--floating {
    position: fixed;
}


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
.toggle.checked {
  --ray-size: calc(var(--size) * -0.4);
  --offset-orthogonal: calc(var(--size) * 0.65);
  --offset-diagonal: calc(var(--size) * 0.45);
  transform: scale(0.75);
  color: #ffaa00;
  box-shadow: inset 0 0 0 var(--size), calc(var(--offset-orthogonal) * -1) 0 0 var(--ray-size), var(--offset-orthogonal) 0 0 var(--ray-size), 0 calc(var(--offset-orthogonal) * -1) 0 var(--ray-size), 0 var(--offset-orthogonal) 0 var(--ray-size), calc(var(--offset-diagonal) * -1) calc(var(--offset-diagonal) * -1) 0 var(--ray-size), var(--offset-diagonal) var(--offset-diagonal) 0 var(--ray-size), calc(var(--offset-diagonal) * -1) var(--offset-diagonal) 0 var(--ray-size), var(--offset-diagonal) calc(var(--offset-diagonal) * -1) 0 var(--ray-size);
}
</style>
