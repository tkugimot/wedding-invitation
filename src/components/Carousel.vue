<template>
    <v-carousel
            cycle
            height="auto"
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
                        <h1 id="heading03">Wedding Invitation</h1>
                    </div>
                </v-row>
<!--            </v-sheet>-->
        </v-carousel-item>
    </v-carousel>
</template>

<style scoped>
    .v-image {
        height: 100% !important;
    }
    .v-carousel--hide-delimiter-background {
        height: 100%;
    }
    h1 {
        font-family: "Waltograph 42";
        /*padding-top: 1000px;*/
        font-size: 60px;
        /*color: black;*/
    }

    @media only screen and (min-width: 750px) {
        #heading03{
            font-size: 128px;
        }
    }
    .title {
        /*padding-top: 1000px;*/
    }
    /* 03.リボン */
    #heading03{
        position:relative;
        /*margin:230px -10px; 真ん中*/
        margin-top: 300px;
        padding:5px;
        /*font:normal 28px/1.6 "Times New Roman", Times, serif;*/
        text-align:center;
        color:#ffe8e8;
        background:#f99;
        -webkit-transform: rotate(-3deg) skew(-3deg);
        -moz-transform: rotate(-3deg) skew(-3deg);
        -o-transform: rotate(-3deg) skew(-3deg);
        transform: rotate(-3deg) skew(-3deg);
        box-shadow:0 1px 2px 0 rgba(0,0,0,0.2);
        background-image: -webkit-gradient(linear, left top, left bottom,
        from(           rgba(0, 0, 0, 0.0)),
        color-stop(0.08, rgba(255, 255, 255, 0.5)),
        color-stop(0.12, rgba(255, 255, 255, 0.5)),
        color-stop(0.12, rgba(0, 0, 0, 0.0)),
        color-stop(0.88, rgba(0, 0, 0, 0.0)),
        color-stop(0.88, rgba(255, 255, 255, 0.5)),
        color-stop(0.92, rgba(255, 255, 255, 0.5)),
        color-stop(0.92, rgba(0, 0, 0, 0.0)),
        to(             rgba(0, 0, 0, 0.0))
        );
        background-image: -moz-linear-gradient(top,
        transparent 8%,
        rgba(255, 255, 255, 0.5) 8%,
        rgba(255, 255, 255, 0.5) 12%,
        transparent 12%,
        transparent 88%,
        rgba(255, 255, 255, 0.5) 88%,
        rgba(255, 255, 255, 0.5) 92%,
        transparent 92%
        );
        background-image: -o-linear-gradient(top,
        transparent 8%,
        rgba(255, 255, 255, 0.5) 8%,
        rgba(255, 255, 255, 0.5) 12%,
        transparent 12%,
        transparent 88%,
        rgba(255, 255, 255, 0.5) 88%,
        rgba(255, 255, 255, 0.5) 92%,
        transparent 92%
        );
        background-image: linear-gradient(to bottom,
        transparent 8%,
        rgba(255, 255, 255, 0.5) 8%,
        rgba(255, 255, 255, 0.5) 12%,
        transparent 12%,
        transparent 88%,
        rgba(255, 255, 255, 0.5) 88%,
        rgba(255, 255, 255, 0.5) 92%,
        transparent 92%
        );
    }
    #heading03:before{
        content:" ";
        position:absolute;
        top:-5px;
        left:0;
        width:0;
        height:0;
        border-width:0 0 5px 10px;
        border-style:solid;
        border-color:transparent;
        border-bottom-color:#c66;
    }
    #heading03:after{
        content:" ";
        position:absolute;
        top:100%;
        right:0;
        width:0;
        height:0;
        border-width:5px 10px 0 0;
        border-style:solid;
        border-color:transparent;
        border-top-color:#c66;
    }

</style>

<script>
    export default {
        name: "Carousel",
        data () {
            return {
                items: [
                    {
                        src: require('../assets/images/118_low.jpg'),
                    },
                    {
                        src: require('../assets/images/090_low.jpg'),
                    },
                    {
                        src: require('../assets/images/005_low.jpg'),
                    },
                    {
                        src: require('../assets/images/114_low.jpg'),
                    },
                ],
            }
        },
    }
</script>

