<template>
    <div>
        <v-app-bar class="bg-color1">
            <NuxtLink :to="{ name: 'index' }" class="nav-link">
                <v-toolbar-title class="text-white">Logo</v-toolbar-title>
            </NuxtLink>

            <NuxtLink
                :to="{ name: 'stores-all-shops' }"
                class="nav-link text-white"
            >
                جميع المتاجر
            </NuxtLink>

            <v-spacer></v-spacer>

            <v-app-bar-nav-icon
                class="text-white"
                @click.stop="drawer = !drawer"
            ></v-app-bar-nav-icon>
        </v-app-bar>

        <v-navigation-drawer
            v-model="drawer"
            absolute
            bottom
            temporary
            :right="$vuetify.rtl ? false : true"
        >
            <v-list nav dense>
                <v-list-item-group
                    v-model="group"
                    active-class="deep-purple--text text--accent-4"
                >
                    <NuxtLink :to="{ name: 'index' }">
                        <v-list-item>
                            <v-list-item-title> Foo </v-list-item-title>
                        </v-list-item>
                    </NuxtLink>

                    <v-list-item>
                        <v-list-item-title>Bar</v-list-item-title>
                    </v-list-item>

                    <v-list-item>
                        <v-list-item-title>Fizz</v-list-item-title>
                    </v-list-item>

                    <v-list-item>
                        <v-list-item-title>Buzz</v-list-item-title>
                    </v-list-item>
                </v-list-item-group>
            </v-list>
        </v-navigation-drawer>
    </div>
</template>

<script>
export default {
    data: () => ({
        drawer: false,
        group: null
    }),

    watch: {
        group() {
            this.drawer = false
        }
    }
}
</script>
