<template>
    <v-sheet color="white" elevation="1" rounded class="px-4 py-2">
        <v-checkbox v-model="selected" label="John" value="John" class="mt-2" hide-details></v-checkbox>
        <v-checkbox v-model="selected" label="Jacob" value="Jacob" class="mt-2" hide-details></v-checkbox>
        <v-checkbox v-model="selected" label="esam" value="esam" class="mt-2" hide-details></v-checkbox>
    </v-sheet>
</template>

<script>
export default {
    data() {
        return {
            selected: ['John', 'esam']
        }
    }
}
</script>
