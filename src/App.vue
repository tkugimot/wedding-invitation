<template>
    <v-app id="app">
        <div class="back">
            <div id="top"></div>
            <Carousel/>
            <v-row
                    class="top-links"
                    align="center"
                    justify="space-around"
            >
                <v-col class='top-tab'>
                    <v-btn large text color="red" href="#greeting" v-smooth-scroll>ご挨拶</v-btn>
                </v-col>
                <v-col class='top-tab'>
                    <v-btn large text color="red" href="#event" v-smooth-scroll>日時・会場</v-btn>
                </v-col>
                <v-col class='top-tab'>
                    <v-btn large text color="red" href="#attend" v-smooth-scroll>ご出欠</v-btn>
                </v-col>
            </v-row>

            <div id="greeting">
                <Message/>
            </div>
            <div id="event">
                <Event/>
            </div>
            <div id="attend">
                <AttendForm/>
            </div>
            <Footer/>
        </div>
    </v-app>
</template>

<style>
    /* Google fontsで導入したいfonts から@importのコードを取得 */
    @import url('https://fonts.googleapis.com/css?family=Kosugi&display=swap');
    #app {
        /* Google fontsで導入したいfontsからfont-familyを取ってくる */
        font-family: 'Kosugi', cursive;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: white;
        overflow: hidden;
    }

    @media only screen and (min-width: 750px) {
        #app {
            background-color: #fff5f7;
            /*background-image:*/
            /*    !*radial-gradient(#ffbcbc 20%, transparent 20%),*!*/
            /*        radial-gradient(#ffe0e0 50%, transparent 50%);*/
            /*background-repeat: repeat;*/
            /*background-size: 75px 75px;*/
            /*background-position: 0 0, 20px 20px;*/
        }
        .back {
            width: 900px;
            max-width: 100%;
            margin: 0 auto;
        }
    }
    .top-links {
        margin: 0 !important;
    }
    .top-tab {
        background-color: #ffffff;
    }
</style>

<script>
import './assets/sass/style.scss'
import Carousel from "./components/Carousel";
import Message from "./components/tabs/Message";
import Event from "./components/tabs/Event";
import AttendForm from "./components/tabs/AttendForm";
import vueSmoothScroll from 'vue-smooth-scroll';
import Vue from 'vue';
import Footer from "./components/Footer";
import * as VueGoogleMaps from 'vue2-google-maps'

Vue.use(vueSmoothScroll);
Vue.use(VueGoogleMaps, {
    load: {
        key: process.env.VUE_APP_GOOGLE_MAP_API,
        libraries: 'places',
        region: 'JP',
        language: 'ja'
    }
});
new Vue({
});

export default {
  name: 'App',

  components: {
      Footer,
      Carousel,
      Message,
      Event,
      AttendForm
  },

  data() {
      return {
          tab: null
      }
  }
};
</script>
