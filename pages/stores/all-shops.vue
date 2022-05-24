<template>
    <v-main>
        <div
            class="page-header text-center"
            :data-src="require(`~/assets/images/page-header-bg.jpeg`)"
            lazy="loaded"
            :style="{ backgroundImage: `url(${require('@/assets/images/page-header-bg.jpeg')})` }"
        >
            <div class="container">
                <h1 class="page-title">جميع <span>المتاجر</span></h1>
            </div>
        </div>
        <v-container>
            <AllStores :stores="stores" :columns="columns"></AllStores>
        </v-container>
    </v-main>
</template>

<script>
import AllStores from '../../components/stores/AllStores.vue'
export default {
    name: 'AllShopsPage',

    components: { AllStores },

    layout: 'DefaultLayout',

    data() {
        return {
            columns: 'col-lg-4 col-md-4 col-sm-6 col-xs-12',
            bgImage: require(`~/assets/images/page-header-bg.jpeg`),
            stores: [
                {
                    id: 1,
                    name: 'Store 1',
                    logo: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg',
                    shortDescription: 'محل للملابس الاطفالى',
                    address: 'المنشية جنب السنترال',
                    phone: '123-456-7890',
                    hours: [
                        {
                            day: 'السبت',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الاحد',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الاثنين',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الثلاثاء',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الاربعاء',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الخميس',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الجمعة',
                            open: '9ص',
                            close: '12م'
                        }
                    ],
                    products: [
                        {
                            id: 1,
                            name: 'Product 1',
                            description:
                                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
                            price: '$10.00',
                            image: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'
                        },
                        {
                            id: 2,
                            name: 'Product 2',
                            description:
                                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
                            price: '$10.00',
                            image: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'
                        }
                    ],
                    reviews: [
                        {
                            id: 1,
                            rating: 5,
                            comment:
                                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
                        },
                        {
                            id: 2,
                            rating: 4,
                            comment:
                                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
                        }
                    ],
                    reviewsCount: 2,
                    rating: 4.5,
                    ratingCount: 2,
                    isFavorite: false,
                    isOpen: true,
                    isNew: false,
                    isPopular: false,
                    isFeatured: false,
                    isDelivery: false
                },
                {
                    id: 2,
                    name: 'Store 2',
                    logo: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg',
                    shortDescription: 'محل ادوات كهربائية',
                    address: 'شارع الثورة خلف جمعة',
                    phone: '123-456-7890',
                    hours: [
                        {
                            day: 'السبت',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الاحد',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الاثنين',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الثلاثاء',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الاربعاء',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الخميس',
                            open: '9ص',
                            close: '12م'
                        },
                        {
                            day: 'الجمعة',
                            open: '9ص',
                            close: '12م'
                        }
                    ],
                    products: [
                        {
                            id: 1,
                            name: 'Product 1',
                            description:
                                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
                            price: '$10.00',
                            image: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'
                        },
                        {
                            id: 2,
                            name: 'Product 2',
                            description:
                                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
                            price: '$10.00',
                            image: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'
                        }
                    ],
                    reviews: [
                        {
                            id: 1,
                            rating: 5,
                            comment:
                                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
                        },
                        {
                            id: 2,
                            rating: 4,
                            comment:
                                'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
                        }
                    ],
                    reviewsCount: 2,
                    rating: 4.5,
                    ratingCount: 2,
                    isFavorite: false,
                    isOpen: true,
                    isNew: false,
                    isPopular: false,
                    isFeatured: false,
                    isDelivery: false
                }
            ]
        }
    }
}
</script>
