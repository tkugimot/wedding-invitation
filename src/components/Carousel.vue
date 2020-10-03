<template>
    <v-carousel
            cycle
            height="600"
            hide-delimiter-background
            show-arrows-on-hover
            hide-delimiters
    >
        <v-carousel-item
                v-for="(item,i) in items"
                :key="i"
                :src="item.src"
        ></v-carousel-item>
    </v-carousel>
</template>

<script>
    export default {
        name: "Carousel",
        data () {
            return {
                items: [
                    {
                        src: require('../assets/images/2.jpg'),
                    },
                    {
                        src: require('../assets/images/3.jpg'),
                    },
                    {
                        src: require('../assets/images/4.jpg'),
                    },
                    {
                        src: require('../assets/images/088.jpg'),
                    },
                ],
            }
        },
    }
</script>

<style scoped>

</style>
