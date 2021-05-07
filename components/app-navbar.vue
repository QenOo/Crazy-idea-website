<template>
    <div class="my-navbar">
            <!-- Nav bar -->
            <v-app-bar height="100px" app>
        <v-container class="pa-0 fill-height">


                <v-toolbar-title>

                    <v-img v-if=" this.$vuetify.theme.dark == false" src="/logo.svg" width="70px" ></v-img>
                    <v-img v-else src="/logow.svg" width="60px" ></v-img>
                </v-toolbar-title>

                <v-spacer></v-spacer>
                
                <v-app-bar-nav-icon class="hidden-md-and-up" @click="drawer = true"></v-app-bar-nav-icon>
                
                <v-toolbar-items class="hidden-sm-and-down">
                        
                    <v-btn text v-for="item in menuItems" :key="item.index" :to="item.path">
                        <v-icon small > {{ item.icon }} </v-icon>
                        <span> {{$t(`${item.title}`)}} </span>
                    </v-btn>

                    
                </v-toolbar-items>



        </v-container>
            </v-app-bar>
        <v-navigation-drawer v-model="drawer" absolute temporary>

            <v-list nav dense>
                <v-list-item-group v-model="group" active-class="textinfo--text text--accent-4" >

                    <v-list-item v-for="item in menuItems" :key="item.index" :to="item.path">
                        <v-list-item-icon>
                            <v-icon> {{ item.icon }} </v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>
                            {{$t(`${item.title}`)}}
                        </v-list-item-title>
                    </v-list-item>

                </v-list-item-group>
            </v-list>

        </v-navigation-drawer>
        <!-- Nav bar -->

        
    </div>
</template>

<script>
export default {

    data() {
        return {
            drawer: false,
            group: null,
            menuItems: [
                {title: 'home', path: '/', icon: 'mdi-home'},
                {title: 'aboutUs', path: '/about-us', icon: 'mdi-shield-account'},
                {title: 'services', path: '/services', icon: 'mdi-face-agent'},
                {title: 'projects', path: '/projects', icon: 'mdi-account-group'},
                {title: 'works', path: '/works', icon: 'mdi-briefcase'},
                {title: 'blog', path: '/blog', icon: 'mdi-shield-account'},
                {title: 'contactUs', path: '/contact-us', icon: 'mdi-shield-account'},
            ]
        };
    }
};
</script>


<style>
.v-navigation-drawer {
    max-height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
}

.v-btn--active:before,
.v-btn:hover {
    background-color: transparent;
    border-bottom: 4px solid transparent;
    opacity: 1;
}

.v-btn:hover {
    background-color: #006eff77;
}

.v-btn--active:before {
    border-bottom: 4px solid #428EF3;
}
.v-btn {
    border-bottom: 4px solid transparent;
}

a.v-btn--active span {
    color: #428EF3;
}

.theme--dark.v-btn--active:hover::before, .theme--dark.v-btn--active::before,
.theme--light.v-btn--active:hover::before, .theme--light.v-btn--active::before {
    opacity: 1;
}

</style>