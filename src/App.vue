<template>
  <div class="app">
    <TheHeader title="The Anime Quoter" />
    <TheQuote />
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
  }
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
