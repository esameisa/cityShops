<template>
    <v-main>
        <v-container>
            <v-row>
                <v-col>
                    <div class="h1">Store Details Page {{ this.$route.params.slug }}</div>
                </v-col>
            </v-row>
        </v-container>
    </v-main>
</template>

<script>
export default {
    name: 'StoreDetailsPage',

    layout: 'DefaultLayout'
}
</script>
