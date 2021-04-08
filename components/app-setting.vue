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
                <v-btn v-model="fab" color="blue lighten-3" depressed x-large dark fab>
                    <v-icon blue v-if="fab">
                        mdi-close
                    </v-icon>
                    <v-img v-else max-width="40px" src="/flagLang/settings.svg"></v-img>
                </v-btn>
            </template>
            


            <v-btn
                fab
                dark
                large
                icon
                @click.stop="toggle_dark_mode"
            >
                <!-- <v-icon>mdi-plus</v-icon> -->
                    <input class="toggle" type="checkbox">
                
            </v-btn>

            <btn-app-setting />
        </v-speed-dial>
    </v-card>
</template>

<script>

import btnAppSetting from './btn-app-setting.vue';
export default {
    components: { btnAppSetting },

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
        transition: "scale-transition"
    }),

    methods: {
        toggle_dark_mode () {
            this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
            localStorage.setItem("dark_theme", this.$vuetify.theme.dark.toString());
        }
    },

};
</script>

<style>
/* This is for documentation purposes and will not be needed in your application */
#create .v-speed-dial {
  position: absolute;
  bottom: 50px;
}

#create .v-btn--floating {
  position: relative;
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
