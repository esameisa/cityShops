<template>
    <v-row>
        <v-col v-for="store in stores" :key="store.id" :class="columns">
            <v-card class="mx-auto my-12">
                <template slot="progress">
                    <v-progress-linear
                        color="deep-purple"
                        height="10"
                        indeterminate
                    ></v-progress-linear>
                </template>

                <v-img height="250" :src="store.logo"></v-img>

                <v-card-title class="pb-1 fs-4">
                    <NuxtLink
                        class="text-decoration-none text-body"
                        :to="{
                            name: 'stores-slug',
                            params: { slug: store.id }
                        }"
                    >
                        {{ store.name }}‎
                    </NuxtLink>
                </v-card-title>

                <v-card-text class="py-0 mt-0 mb-2">{{
                    store.shortDescription
                }}</v-card-text>

                <v-card-text class="py-0 mt-0 mb-2">
                    <v-row align="center" class="mx-0 mt-1">
                        <ul class="list-unstyled ps-0 mx-0">
                            <li class="d-inline-block">
                                <v-rating
                                    :value="store.rating"
                                    color="amber"
                                    dense
                                    half-increments
                                    readonly
                                    size="20"
                                ></v-rating>
                            </li>
                            <li class="d-inline-block">
                                <div class="grey--text ms-0">
                                    ({{ store.reviews.length }})
                                </div>
                            </li>
                        </ul>
                    </v-row>

                    <div class="my-1">العنوان: {{ store.address }}</div>
                </v-card-text>

                <v-divider class="mx-4 mt-4 mb-0"></v-divider>

                <div v-if="store.hours">
                    <div v-if="store.hours.length">
                        <v-card-title class="py-2">مواعيد العمل</v-card-title>

                        <v-card-text>
                            <v-chip-group
                                v-model="selection"
                                active-class="bg-color3 accent-4 white--text"
                                column
                            >
                                <v-chip
                                    v-for="hour in store.hours"
                                    :key="hour.day"
                                >
                                    <span class="me-1">{{ hour.day }}</span>
                                    <span>
                                        {{ hour.open }} الى {{ hour.close }}
                                    </span>
                                </v-chip>
                            </v-chip-group>
                        </v-card-text>
                    </div>
                </div>
            </v-card>
        </v-col>
    </v-row>
</template>

<script>
export default {
    props: {
        stores: {
            type: Array,
            required: true
        },
        columns: {
            type: String,
            default: () => 'col-lg-4 col-md-4 col-sm-6 col-xs-12'
        }
    },

    data() {
        return {
            selection: new Date().getDay() + 1 ?? null
        }
    }
}
</script>
