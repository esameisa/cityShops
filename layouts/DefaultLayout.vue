<template>
    <v-app>
        <ToolBar />
        <Nuxt />
        <MainFooter />
    </v-app>
</template>

<script>
import ToolBar from '../components/ToolBar.vue'
import MainFooter from '../components/MainFooter.vue'

export default {
    name: 'App',

    components: { ToolBar, MainFooter },

    layout: 'DefaultLayout'
}
</script>
