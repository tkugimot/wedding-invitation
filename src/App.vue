<template>
    <v-app id="app">
        <div id="top"></div>
        <Carousel/>
        <v-row
                class="top-links"
                align="center"
                justify="space-around"
        >
            <v-col>
                <v-btn large text color="pink" href="#greeting" v-smooth-scroll>ご挨拶</v-btn>
            </v-col>
            <v-col>
                <v-btn large text color="pink" href="#event" v-smooth-scroll>日時・会場</v-btn>
            </v-col>
            <v-col>
                <v-btn large text color="pink" href="#attend" v-smooth-scroll>ご出欠</v-btn>
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
    </v-app>
</template>

<style>
    /* Google fontsで導入したいfonts から@importのコードを取得 */
    @import url('https://fonts.googleapis.com/css?family=Noto+Sans+JP&display=swap');
    #app {
        /* Google fontsで導入したいfontsからfont-familyを取ってくる */
        font-family: 'Noto Sans JP', cursive;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        overflow: hidden;
    }
</style>

<script>
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
