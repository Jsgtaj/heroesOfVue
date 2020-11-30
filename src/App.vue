<template>
  <div id="app">
    <main class="mw6 center">
      <add-hero-button @add-hero="addHero" btn-txt="Add Hero"/>
     <twitter-short-profile  v-for="hero in heroes" :key="hero.name" :thishero="hero"/>
    </main>
  </div>
</template>

<script>
import AddHeroButton from './components/AddHeroButton.vue';
import TwitterShortProfile from "./components/TwitterShortProfile.vue";

export default {
  name: 'App',
  components: {
    TwitterShortProfile,
    AddHeroButton
  },
  data(){
    return{
      startArr: [
      {
        name: "Prof. Xavier",
        twitter: "@profx",
        pic:
          "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0004.gif"
      },
      {
        name: "Spiderman",
        twitter: "@spidey",
        pic:
          "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0008.gif"
      },
      {
        name: "Wolverine",
        pic:
          "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0011.gif",
        twitter: "@logan"
      },
      {
        name: "Cyclops",
        twitter: "@oneye",
        pic:
          "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0005.gif"
      },
      {
        name: "Storm",
        twitter: "@rainsitpours",
        pic:
          "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0007.gif"
      },
      {
        name: "Phoenix",
        twitter: "@jeangrey",
        pic:
          "http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0016.gif"
      }
    ],
      heroes: []
    };
  },
  methods: {
    addHero(){
      this.startArr.length > 0 && this.heroes.push(this.startArr.shift());
    }
  }
}
</script>