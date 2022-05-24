<template>
    <v-sheet
        :color="`grey ${$vuetify.theme.isDark ? 'darken-2' : 'lighten-4'} ${
            placeholder ? 'd-block' : 'd-none'
        }`"
        class="pa-3"
    >
        <v-skeleton-loader
            class="mx-auto"
            max-width="300"
            type="card"
        ></v-skeleton-loader>
    </v-sheet>
</template>

<script>
export default {
    props: {
        placeholder: {
            type: Boolean,
            default: () => true
        }
    }
}
</script>
