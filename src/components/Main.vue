<template>
  <main v-bind:class="theme">
    <Products v-bind:isLight="isLight" />
    <About />
  </main>
</template>
<script>
import Products from './main/Products';
import About from './main/About';
export default {
  name: 'Main',
  components: {
    Products,
    About,
  },
  props: {
    isLight: Boolean,
    themeClass: String,
  },
  computed: {
    theme: function() {
      return this.isLight ? 'lighter container' : 'dark container';
    },
  },
};
</script>
<style scoped></style>
