<template>
<div>
    <img src="@/assets/img/ui/logo.png" alt="Outsider" id="logo" v-bind:class="{ visible: showLogo }">
    <a href="#" v-on:click="toggleMenu"><img src="@/assets/img/ui/burger.svg" alt="Open menu" id="burger"></a>  
    <div class="lang-switch" v-if="!isMobile">
      <a href="#" v-on:click="switchLang('en', $event)" v-bind:class="{ active: lang == 'en' }">EN</a>
      /
      <a href="#" v-on:click="switchLang('fr', $event)" v-bind:class="{ active: lang == 'fr' }">FR</a>
    </div>

    <div id="menu" v-bind:class="{ visible: menuVisible }">
      <ul>
        <li><a href="#" v-on:click="scrollTo('#album')">ALBUM</a></li>
        <li><a href="#" v-on:click="scrollTo('#videos')">VIDEOS</a></li>
        <li><a href="#" v-on:click="scrollTo('#podcasts')">PODCASTS</a></li>
        <li><a href="#" v-on:click="scrollTo('#tour')">DATES</a></li>
        <li><a href="#" v-on:click="scrollTo('#press')">PRESS</a></li>
        <li><a href="#" v-on:click="scrollTo('#shop')">SHOP</a></li>
        <li><a href="/henry-darger-collections.html" target="_blank">DARGER MAP</a></li>
        <li><a href="https://yabasta-records.com/outsider-lyric" target="_blank">LYRICS</a></li>
        <li><a href="#" v-on:click="scrollTo('#contact')">CONTACT</a></li>
      </ul>
      <a href="#" v-on:click="toggleMenu" class="bt-close"><img src="@/assets/img/ui/close.svg" alt="Close menu"></a>
      <div class="lang-switch" v-if="isMobile">
        <a href="#" v-on:click="switchLang('en', $event)" v-bind:class="{ active: lang == 'en' }">EN</a>
        /
        <a href="#" v-on:click="switchLang('fr', $event)" v-bind:class="{ active: lang == 'fr' }">FR</a>
      </div>
    </div>

    <div id="mask-top"></div>
    <div id="mask-bottom"></div>
    <div id="mask-left"></div>
    <div id="mask-right"></div>
</div>
  
</template>

<script>
import $ from 'jquery'
import { EventBus } from "@/event-bus.js"

export default {
  name: 'Frame',
  data() {
    return {
      menuVisible: false,
      showLogo: true,
      isMobile: false,
      lang: 'en'
    }
  },
  created(){
    let that = this

    // if mobile
    if(window.innerWidth >= 1024)
      window.addEventListener('scroll', toggleLogo)

    function toggleLogo() {
      if(window.pageYOffset > 1500)
        that.showLogo = true
      else
        that.showLogo = false
    }

    if(window.innerWidth <= 414)
      this.isMobile = true

    EventBus.$on('langChanged', this.langChangedHandler)
  },
  methods: {
    toggleMenu(e) {
      e.preventDefault()

      if(!this.menuVisible)
        this.menuVisible = true
      else
        this.menuVisible = false
    },
    scrollTo(id){
      $([document.documentElement, document.body]).animate({
        scrollTop: $(id).offset().top - window.innerHeight/1.7
      }, 2000);
    },
    switchLang(lang, e){
      e.preventDefault()
      EventBus.$emit('langChanged', lang)
    },
    langChangedHandler(lang){
      this.lang = lang
    }
  }
}
</script>