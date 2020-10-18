<template>
    <v-carousel
            cycle
            height="300"
            hide-delimiter-background
            show-arrows-on-hover
            hide-delimiters
    >
        <v-carousel-item
                v-for="(item,i) in items"
                :key="i"
                :src="item.src"
        >
<!--            <v-sheet-->
<!--                    height="100%"-->
<!--                    tile-->
<!--            >-->
                <v-row
                        class="fill-height"
                        align="center"
                        justify="center"
                >
                    <div class="title">
                        <h1>Wedding Invitation</h1>
                    </div>
                </v-row>
<!--            </v-sheet>-->
        </v-carousel-item>
    </v-carousel>
</template>

<style scoped>
    h1 {
        font-family: "Waltograph 42";
        padding-top: 200px;
        font-size: 50px;
        color: black;
    }
</style>

<script>
    export default {
        name: "Carousel",
        data () {
            return {
                items: [
                    {
                        src: require('../assets/images/005_low_mozaik.jpg'),
                    },
                    {
                        src: require('../assets/images/090_low_mozaik.jpg'),
                    },
                    {
                        src: require('../assets/images/073_low_mozaik.jpg'),
                    },
                    {
                        src: require('../assets/images/114_low_mozaik.jpg'),
                    },
                ],
            }
        },
    }
</script>

