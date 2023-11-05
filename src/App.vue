<template>
  <div class="app">
    <TheHeader title="The Anime Quoter" />
    <TheQuote :quote="quote" />
    <div class="button-container">
      <button @click="getQuote">Generate</button>
    </div>
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

.button-container {
  display: flex;
  justify-content: center;
  padding: 0 32px;
  margin: 64px auto;

  button {
    border: none;
    outline: none;
    background-color: var(--primary);
    padding: 16px 32px;
    border-radius: 99px;
    color: var(--light);
    font-size: 28px;
    font-weight: 700;
    text-transform: uppercase;
    cursor: pointer;
    transition: 0.4s;

    &:hover {
      background-color: var(--secondary);
    }
  }
}
</style>
