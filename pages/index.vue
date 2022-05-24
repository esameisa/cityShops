<template>
    <div>
        <v-container fluid class="my-5">
            <v-row>
                <v-col sm="6" md="2" xl="2">
                    <ProductsFilter />
                </v-col>

                <v-col sm="6" md="10" xl="10">
                    <v-row>
                        <v-col sm="6" md="3" xl="2" v-for="n in 7" :key="n">
                            <MainCard
                                :title="title"
                                :image="image"
                                :slides="slides"
                                :rating="
                                    parseFloat(Math.random() * (5 - 1) + 1)
                                "
                                :price="Math.random() * (1000 - 100) + 100"
                                :description="description"
                            />
                        </v-col>
                    </v-row>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
import MainCard from '../components/MainCard.vue'
import ProductsFilter from '../components/ProductsFilter.vue'
export default {
    name: 'IndexPage',

    components: { MainCard, ProductsFilter },

    layout: 'DefaultLayout',

    data() {
        return {
            title: 'موبايل سامسونج جالاكسي نوت 20 الترا بشريحتين اتصال هايبريد، شاشة 6.9 بوصة، 256 جيجابايت، رام 8 جيجابايت، شبكة الجيل الرابع ال تي اي، بطارية 4500 مللي امبير في الساعة - برونزي ميستيك',
            image: require(`~/assets/images/carousel-placeholder.webp`),
            description:
                'خصم 15٪ على طلب التطبيق الأول. كود APP15 <br /> احصل عليه الأربعاء, 4 مايو <br /> تشحن من اسم المحل - شحن مجاني',
            slides: [
                {
                    src: require(`~/assets/images/carousel-placeholder.webp`),
                    alt: '',
                    link: ''
                },
                {
                    src: require(`~/assets/images/carousel-placeholder.webp`),
                    alt: '',
                    link: ''
                },
                {
                    src: require(`~/assets/images/carousel-placeholder.webp`),
                    alt: '',
                    link: ''
                },
                {
                    src: require(`~/assets/images/carousel-placeholder.webp`),
                    alt: '',
                    link: ''
                }
            ]
        }
    }
}
</script>
