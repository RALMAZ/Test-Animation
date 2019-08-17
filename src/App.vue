<template>
  <div id="app">
    <div
      class="header"
    >
      <div>
        <div
          ref="logo"
          class="logo"
        ></div>
      </div>
      <div class="logo-text">
        Terra infinity
      </div>
    </div>

    <div class="body">
      <ScrollButton/>
      <TechBlock/>
      <div class="fullpage-container">
        <div
          v-fullpage="opts"
          ref="fullpage"
          class="fullpage-wp view-pc"
        >
          <div
            v-for="(page, i) in pages"
            :key="i"
            :class="[page.class]"
            class="page" 
          >

            <div
              v-animate="{value: animation}"
              :ref="'page' + i"
            >
              <div
                v-html="page.title"
                class="title"
              ></div>
              <div
                v-html="page.desk"
                class="desk"
              ></div>
              <div
                v-html="page.desk.replace(/\<br\/\>/g, ' ')"
                class="desk-mobile"
              ></div>
              <div v-animate="{value: animation, delay: 900}">
                <div
                  v-text="page.actionText"
                  class="action"
                ></div>
                <div
                  v-text="page.email"
                  class="email"
                ></div>
              </div>
            </div>

          </div>
        </div>
        
        <div
          v-fullpage="opts"
          ref="fullpage"
          class="fullpage-wp view-mobile"
        >
          <div
            v-for="(page, i) in mobile"
            :key="i"
            :class="[page.class]"
            class="page" 
          >

            <div
              v-animate="{value: animation}"
              :ref="'page' + i"
            >
              <div
                v-html="page.title"
                class="title"
              ></div>
              <div
                v-html="page.desk"
                class="desk"
              ></div>
              <div
                v-html="page.mobile"
                class="desk-mobile"
              ></div>
              <div
                v-html="page.desk.replace(/\<br\/\>/g, ' ')"
                class="desk-mobile"
              ></div>
              <div v-animate="{value: animation, delay: 900}">
                <div
                  v-text="page.actionText"
                  class="action"
                ></div>
                <div
                  v-text="page.email"
                  class="email"
                ></div>
              </div>
            </div>

          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
import lottie from 'lottie-web';
import pagesData from '@/assets/data/pages.json';
import mobileData from '@/assets/data/mobile.json';

import ScrollButton from '@/components/ScrollButton.vue';
import TechBlock from '@/components/TechBlock.vue';
import { log } from 'util';

export default {
  components: {
    ScrollButton,
    TechBlock
  },

  data() {
    return {
      pages: [],
      mobile: [],

      animation: 'fadeInUp',

      opts: {
        start: 0,
        dir: 'v',
        der : 0.1,
        movingFlag : false,
        duration: 500,
        beforeChange: (prev, current, next) => {
          //this.animationDirection(current, next);
        },
        afterChange: (prev, next) => {}
      }
    }
  },

  methods: {
    animationDirection(current, next) {
      if (current < next) {
        this.animation = 'fadeInUp';
      } else {
        this.animation = 'fadeInDown';
      }
      this.$refs.fullpage.$fullpage.$update();
    },

    pageWidth() {
      return document.width;
    }
  },

  created() {
    this.pages = pagesData;
    this.mobile = mobileData;
  },

  mounted() {
    lottie.loadAnimation({
      container: this.$refs.logo,
      renderer: 'svg',
      loop: true,
      autoplay: true,
      path: './terra_logo.json'
    });

    console.log(this.$refs.fullpage.$fullpage);
  }
}
</script>

<style lang="scss">
  @import "./css/main.css";
  @import "./css/media.scss";
</style>