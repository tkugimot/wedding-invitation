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
                            <h2>日時・会場</h2>
                            <v-container>
                                <div>
                                    <p>
                                        挙式
                                        2021.03.27
                                        17:15~

                                        披露宴
                                        19:00~
                                    </p>
                                </div>
                            </v-container>
                            <v-btn
                                    color="yellow"
                                    href="https://tokyo.angelion.jp/"
                            >
                                ANGELION AU PLAZA TOKYO
                            </v-btn>
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
        background-size: contain;
        background-repeat: repeat-y;
        background-image: url(../../assets/images/background.jpg);
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
