<template>
  <div class="app">
    <TheHeader title="The Anime Quoter" />
    <TheQuote :quote="quote" />
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheQuote from '@/components/TheQuote.vue';
export default {
  name: 'App',
  components: {
    TheHeader,
    TheQuote,
  },
  data() {
    return {
      quote: {
        content: 'Content goes here',
        anime: 'Naruto',
        character: 'Madara'
      },
      quotes: [],
    }
  },
  methods: {
    async getQuote() {
      const data = await fetch('https://animechan.xyz/api/random').then(res => res.json());
      this.quote = {
        content: data.quote,
        anime: data.anime,
        character: data.character
      }
    }
  },
  created () {
    // this.getQuote();
  },
}
</script>

<style lang="scss">
:root {
  --primary: #D81E5B;
  --secondary: #8A4FFF;
  --tertiary: #32CBFF;
  --dark: #131A26;
  --light: #EEE;
  --grey: #848484;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Fira Sans', sans-serif;
}
</style>
