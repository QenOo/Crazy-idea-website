<template>
    <div class="works">
        <!--start head-section-page -->
        <div class="head-section-page">

            <v-container>
                <v-row class="d-flex align-center">
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <img src="/pagesImages/services.svg">
                    </v-col>
                    <v-col cols="12" lg="6" md="6" sm="6" xm="12">
                        <h2>{{$t('works')}}</h2>
                    </v-col>
                </v-row>
            </v-container>
            
        </div>
        <!--end head-section-page -->





        <div class="container">
            <h2 class="text-center my-16 head-sec-work headingtow--text">{{$t('recentWorks')}}</h2>
            <div class="filter d-flex align-center">
                <label :class="{ active: selectedCategory === 'All' }">
                    <input type="radio" v-model="selectedCategory" value="All" /> All
                </label><br />
                <label :class="{ active: selectedCategory === 'Web Application' }">
                    <input type="radio" v-model="selectedCategory" value="Web Application" /> Web Application
                </label><br />
                <label :class="{ active: selectedCategory === 'mobileApp' }">
                    <input type="radio" v-model="selectedCategory" value="mobileApp" /> Mobile Application
                </label><br />
                <label :class="{ active: selectedCategory === 'seo' }">
                    <input type="radio" v-model="selectedCategory" value="seo" /> Seo
                </label><br />
            </div>
            
            <v-row>
                <v-col v-for="app in filteredApps" :key="app.id" class="d-flex align-center my-16" cols="12" md="3">
                    <div class="myApp">
                        <img :src="$images(app.image, 'org')" />
                        <h4>{{app.title}}</h4>
                        <span class="textinfo--text">{{app.category}}</span>
                    </div>
                </v-col>
            </v-row>
        </div>




    </div>
</template>

<script>
export default {
    head() {
        return {
            title: this.$t('works')
        }
    },
    data: () => ({
        myApps: [],
		selectedCategory: "All",
    }),
    mounted() {
        this.fetchSomething();
    },
    methods: {
        async fetchSomething() {
            let url = process.env.moduleUrl + 'works';
            const res = await this.$axios.$get(url);
            this.myApps = res.payload.data;

        },
    },
    computed: {
        filteredApps: function() {
            var category = this.selectedCategory;
			if(category === "All") {
                return this.myApps;
			} else {
                return this.myApps.filter(({id, image, title, category, created_at, updated_at}) => category == this.selectedCategory)
			}
		}
	}
}
</script>

<style>
.myApp {
    width: 100%;
    height: 100%;
    text-align: center;
}

.myApp h4 {
    font-size: 20px;
    margin-top: 20px;
}

.myApp img {
    width: 240px;
    height: 200px;
}

.filter {
    justify-content: center;
    width: 100%;
    margin-bottom: 40px;
}

.filter label {
    margin: 0 10px;
    padding: 10px 20px;
    border-radius: 3px;
    cursor: pointer;
}

.filter label.active {
    color: #fff;
    background-color: #4892FF;
}

.filter input {
    visibility: hidden;
    position: absolute;
}

.head-sec-work {
    font-size: 30px;
}
</style>