<template>
    <v-card
            color="white"
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
                        >
                            <img class="icon_image" src="@/assets/images/ribbun.png"/>
                            <h2>ご挨拶</h2>
                        </v-col>
                    </v-row>
                    <v-row
                            no-gutters
                            class="mt-12"
                    >
                        <v-col
                                sm="12"
                                md="12"
                                lg="12"
                                xl="12"
                        >
                            <div class="greeting">
                                <div class="initial_message">
                                    <p>
                                        謹啓<br><br>
                                        新春の候、皆様にはますますご清祥のこととお慶び申し上げます。<br><br>
                                        この度、結婚式を執り行うことになりました。<br><br>つきましては、日頃お世話になっております皆様に、私どもの門出をお見守りいただきたく、ささやかながら小宴を催したく存じます。<br><br>
                                        未曾有の災禍の中、誠に恐縮ではございますが、可能な範囲でご出席いただきたくご案内申し上げます。<br><br>
                                        謹白
                                    </p>
                                </div>
                                <div class="each_profile">
                                    <img class="profile_image" src="@/assets/images/toshi_maru.png"/>
                                    <h2>釘本 寿光</h2>
                                    <h4>くぎもと としみつ</h4>
                                    <div class="each_sentence">
                                        <p>
                                            福岡県出身。パソコンは俺の相棒、ITエンジニア。
                                            香菜ちゃんのズボラ飯が大好き。<br>
                                            中学・高校と野球部一筋。
                                        </p>
                                    </div>
                                </div>


                                <div class="each_profile">
                                    <img class="profile_image" src="@/assets/images/kana_maru.png"/>
                                    <h2>小林 香菜</h2>
                                    <h4>こばやし かな</h4>
                                    <div class="each_sentence">
                                        <p>
                                            埼玉県出身。歯磨きには人一倍うるさい、歯科衛生士。
                                            ディズニーとアイドルが好き。<br>
                                            中学は吹奏楽部、高校は弓道部。
                                        </p>
                                    </div>
                                </div>
                            </div>
                        </v-col>
                    </v-row>
                </v-card>
            </v-container>
        </v-card-text>
    </v-card>
</template>

<style scoped>
    h1 {
        /*font-family: "Waltograph 42";*/
        text-align: center;
    }
    p {
        text-align: left;
    }
    .greeting {
        width: 90%;
        margin: 0 auto;
    }
    .initial_message {

    }
    .each_profile {
        margin: 100px 0;
    }
    .icon_image {
        width: 70px;
        height: 70px;
        margin-bottom: 20px;
    }
    .profile_image {
        width: 180px;
        height: 180px;
    }
    .each_sentence {
        margin-top: 20px;
    }
    .each_sentence p {
        text-align: center;
    }
    .back {
        /*background-size: contain;*/
        /*background-repeat: repeat-y;*/
        /*background-image: url(../../assets/images/background.jpg);*/

        background-color: #fff;
        background-image:
                /*radial-gradient(#ffbcbc 20%, transparent 20%),*/
                radial-gradient(#ffe0e0 50%, transparent 50%);
        background-repeat: repeat;
        background-size: 75px 75px;
        background-position: 0 0, 20px 20px;
    }
</style>
