<template>
    <h1> <h1>{{ $t('aboutUs') }}</h1>
        <nuxt-link :to="switchLocalePath('en')">English</nuxt-link>
        <nuxt-link :to="switchLocalePath('fr')">Français</nuxt-link>
        <nuxt-link :to="switchLocalePath('ar')">arabic</nuxt-link>
    </h1>
</template>

<script>
export default {
    head() {
        return {
            title: this.$t('aboutUs')
        }
    }
}
</script>

<style>

</style>