<template>
    <v-carousel
        :continuous="carousel.continuous"
        :cycle="carousel.cycle"
        :show-arrows="carousel.showArrows"
        hide-delimiter-background
        show-arrows-on-hover
        delimiter-icon="mdi-minus"
        height="300"
        :interval="carousel.interval"
    >
        <v-carousel-item
            v-for="(slide, i) in slides"
            :key="i"
            :src="slide.src"
            exact-active-class
        >
        </v-carousel-item>
    </v-carousel>
</template>
<script>
export default {
    name: 'MainSlider',

    props: {
        slides: {
            type: Array,
            default: () => [
                {
                    src: require(`~/assets/images/carousel-placeholder.webp`)
                }
            ]
        }
    },

    data() {
        return {
            carousel: {
                continuous: true,
                cycle: true,
                showArrows: true,
                interval: 4000
                // interval: Math.randoxm() * (5000 - 3000) + 3000,
            }
        }
    }
}
</script>
