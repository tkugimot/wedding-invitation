<template>
    <v-card
            color="basil"
            flat
            elevation="3"
            class="back"
    >
        <v-card-text>
            <v-container
                    class=""
            >
                <v-card
                        elevation="2"
                        class="grey lighten-5 mt-12 pt-12"
                >
                    <v-row
                            no-gutters
                    >
                        <v-col
                                sm="12"
                                md="12"
                                lg="12"
                                xl="12"
                                class="mb-5"
                        >
                            <img class="icon_image" src="@/assets/images/event.png"/>
                            <h2 class="mb-10">会場・日時</h2>
                            <v-btn
                                    color="error"
                                    href="https://tokyo.angelion.jp/"
                            >
                                ANGELION AU PLAZA TOKYO
                            </v-btn>
                            <v-btn
                                    color="success"
                                    href="https://social-distance.escrit.jp/"
                                    class="mb-5 ma-5"
                            >
                                会場の感染症対策
                            </v-btn>
                            <v-container>
                                <div class="mb-10">
                                    <p>
                                        挙式: 2021.03.27 17:45 〜
                                    </p>
                                    <p>
                                        披露宴: 同日 18:30 〜 21:00
                                    </p>
                                </div>
                            </v-container>
                            <v-container>
                                <div class="mt-10">
                                    <p>
                                        〒104-0031 東京都中央区京橋3-7-1 <br>
                                        相互館110タワー 11F <br>
                                        「東京駅」八重洲南口より徒歩5分 <br>
                                        「京橋駅」2番出口直結 <br>
                                    </p>
                                </div>
                            </v-container>
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col
                                sm="12"
                                md="12"
                                lg="12"
                                xl="12"
                        >
                            <a href="https://g.page/angelion-tk?share">
                                <GmapMap
                                        :center="{lat:35.675757, lng:139.769911}"
                                        :zoom="14"
                                        map-type-id="terrain"
                                        style="width: 100%; height: 300px"
                                >
                                    <GmapMarker
                                            :key="index"
                                            v-for="(m, index) in markers"
                                            :position="m.position"
                                            :clickable="true"
                                            :draggable="true"
                                            @click="center=m.position"
                                    />
                                </GmapMap>
                            </a>
                        </v-col>
                    </v-row>
                </v-card>
            </v-container>
        </v-card-text>
    </v-card>
</template>

<style scoped>
    .back {
        background-color: #fff;
        background-image:
            /*radial-gradient(#ffbcbc 20%, transparent 20%),*/
                radial-gradient(#ffe0e0 50%, transparent 50%);
        background-repeat: repeat;
        background-size: 75px 75px;
        background-position: 0 0, 20px 20px;
    }
    .icon_image {
        width: 70px;
        height: 70px;
        margin-bottom: 20px;
    }
</style>
<script>
    export default {
        name: "HelloWorld",
        data() {
            return {
                markers: [{ position: { lat:35.675757, lng:139.769911 } }]
            };
        },
        methods: {
            onDragEnd() {
                console.log("hoge");
            }
        }
    };
</script>
