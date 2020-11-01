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
                        >
                            <img class="icon_image" src="@/assets/images/syukketsu.png"/>
                            <h2>ご出欠</h2>
                            <div
                                    class="result-message"
                                    v-if="!showForm"
                            >
                                <v-container>
                                    <v-alert type="info"
                                             v-if="result_success === 'yet'"
                                    >
                                        送信中です...🏃‍♂️
                                    </v-alert>
                                    <v-alert type="success"
                                             v-if="result_success === 'success'"
                                    >
                                        送信に成功しました！ 🙆‍♂️
                                    </v-alert>
                                    <v-alert type="error"
                                             v-if="result_success === 'error'"
                                    >
                                        送信に失敗しました。<br> 再度お試しください🙇‍♂️
                                    </v-alert>
                                </v-container>
                            </div>
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
                            <form class="p-form" v-on:submit.prevent="submit" v-if="showForm">
                                <v-container class="pa-5">
                                    <v-radio-group v-model="attend">
                                        <v-radio
                                                :label="`出席`"
                                                :value="0"
                                        ></v-radio>
                                        <v-radio
                                                :label="`オンラインで出席`"
                                                :value="1"
                                        ></v-radio>
                                        <v-radio
                                                :label="`欠席`"
                                                :value="2"
                                        ></v-radio>
                                    </v-radio-group>
                                    <v-text-field
                                            v-model="your_name"
                                            label="お名前"
                                            required
                                    ></v-text-field>
                                    <v-text-field
                                            v-model="zip"
                                            label="郵便番号"
                                            required
                                    ></v-text-field>
                                    <v-text-field
                                            v-model="address"
                                            label="住所"
                                            required
                                    ></v-text-field>
                                    <v-text-field
                                            v-model="phone"
                                            label="電話番号"
                                            required
                                    ></v-text-field>
<!--                                    <v-text-field-->
<!--                                            v-model="email"-->
<!--                                            :rules="emailRules"-->
<!--                                            label="メールアドレス"-->
<!--                                            required-->
<!--                                    ></v-text-field>-->
                                    <v-text-field
                                            v-model="allergy"
                                            label="アレルギー"
                                    ></v-text-field>
                                    <v-textarea
                                            v-model="message"
                                            label="メッセージ"
                                            :counter="100"
                                            auto-grow
                                            outlined
                                            rows="3"
                                            row-height="25"
                                            shaped
                                    ></v-textarea>
                                    <v-btn color="error" type="submit">
                                        送信
                                    </v-btn>
                                </v-container>
                            </form>
                        </v-col>
                    </v-row>
                </v-card>
            </v-container>
        </v-card-text>
    </v-card>
</template>

<style scoped>
    h1 {
        text-align: center;
    }
    p {
        text-align: center;
    }
    /*.back {*/
    /*    background-size: contain;*/
    /*    background-repeat: repeat-y;*/
    /*    background-image: url(../../assets/images/background.jpg);*/
    /*}*/
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
    import Vue from 'vue';
    import axios from "axios";

    new Vue({
    });

    export default {
        name: 'attendForm',

        components: {
        },

        data() {
            return {
                // フォームの表示
                showForm: true,

                // 出欠
                attend: 0,

                // 名前
                your_name: '',

                // 郵便番号
                zip: '',

                // 住所
                address: '',

                // 電話番号
                phone: '',

                // メールアドレス
                // email: '',
                // emailRules: [
                //     value => !!value || 'Required.',
                //     value => (value || '').length <= 50 || '最大50文字です',
                //     value => {
                //         const pattern = /^(([^<>()[\]\\.,;:\s@]+(\.[^<>()[\]\\.,;:\s@]+)*)|(.+))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
                //         return pattern.test(value) || '不正なメールアドレスです'
                //     },
                // ],

                // アレルギー
                allergy: '',

                // メッセージ
                message: '',

                // フォーム送信が成功したかどうか
                result_success: 'yet'
            }
        },
        methods: {
            submit: function() {
                switch (this.attend) {
                    case 0:
                        this.attend = '出席';
                        break;
                    case 1:
                        this.attend = 'オンラインで出席';
                        break;
                    default:
                        this.attend = '欠席';
                }

                const submitParams = new FormData();
                // ご出欠(attend)
                submitParams.append("entry.877086558", this.attend);
                // お名前(name)
                submitParams.append("entry.559352220", this.your_name);
                // 郵便番号(zip)
                submitParams.append("entry.368156127", this.zip);
                // 住所(address)
                submitParams.append("entry.900954813", this.address);
                // 電話番号(phone)
                submitParams.append("entry.1546204373", this.phone);
                // // メールアドレス(email)
                // submitParams.append("entry.78862528", this.email);
                // アレルギー(allergy)
                submitParams.append("entry.1859015822", this.allergy);
                // メッセージ(message)
                submitParams.append("entry.1807093815", this.message);

                // CORSエラー対策
                const CORS_PROXY = "https://cors-anywhere.herokuapp.com/";
                // Googleフォームのaction属性値
                const GOOGLE_FORM_ACTION = "https://docs.google.com/forms/u/0/d/e/1FAIpQLSefANmc7jMEcyWnZVYY9piRaDM152gjK2cZ1ycEU7XiEXWJxg/formResponse";

                // Ajax POST通信
                axios.post(CORS_PROXY + GOOGLE_FORM_ACTION, submitParams).then(() => {
                    // フォーム非表示
                    this.showForm = false;
                    this.result_success = 'success';
                }).catch(() => {
                    this.result_success = 'error';
                });
                // フォーム非表示
                this.showForm = false;
            }
        }
    };
</script>
