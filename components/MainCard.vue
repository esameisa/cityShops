<template>
    <v-card :loading="loading" :class="`mx-auto my-2`">
        <template slot="progress">
            <v-progress-linear
                color="deep-purple"
                height="10"
                indeterminate
            ></v-progress-linear>
        </template>

        <v-img
            height="100%"
            :src="image"
            v-if="imageOrSlides == `image`"
        ></v-img>

        <v-carousel
            :continuous="carousel.continuous"
            :cycle="carousel.cycle"
            :show-arrows="carousel.showArrows"
            hide-delimiter-background
            show-arrows-on-hover
            delimiter-icon="mdi-minus"
            height="300"
            :interval="carousel.interval"
            v-if="imageOrSlides == `slides`"
        >
            <v-carousel-item
                v-for="(slide, i) in slides"
                :key="i"
                exact-active-class
            >
                <v-img height="100%" :src="slide"></v-img>
            </v-carousel-item>
        </v-carousel>

        <v-card-title class="pb-1 fs-6 text-body">
            <NuxtLink
                :to="{ name: 'stores-all-shops', params: { id: '1' } }"
                class="mt-2 fw-bold product-title"
            >
                {{ title }}‎
            </NuxtLink>
        </v-card-title>

        <v-row align="center" class="mx-0 mt-1">
            <ul class="list-unstyled ps-3">
                <li class="d-inline-block">
                    <v-rating
                        :value="this.rating"
                        color="amber"
                        dense
                        half-increments
                        readonly
                        size="20"
                    ></v-rating>
                </li>
                <li class="d-inline-block">
                    <div class="grey--text ms-1">
                        {{ parseFloat(rating).toFixed(2) }}
                    </div>
                </li>
            </ul>
        </v-row>

        <v-card-text class="pt-2">
            <div class="mb-2 fs-4 fw-bold text-body">
                $ {{ parseFloat(price).toFixed(2) }}
            </div>
            <p v-html="description"></p>
        </v-card-text>
    </v-card>
</template>

<script>
export default {
    data: () => ({
        loading: false,
        carousel: {
            continuous: true,
            cycle: false,
            showArrows: true,
            interval: 4000
            // interval: Math.random() * (5000 - 3000) + 3000,
        }
    }),

    props: ['title', 'image', 'slides', 'rating', 'price', 'description'],

    computed: {
        imageOrSlides() {
            if (this.slides.length > 0) {
                return 'slides'
            }
            return 'image'
        }
    }
}
</script>
