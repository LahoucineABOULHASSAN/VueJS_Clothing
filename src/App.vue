<template>
  <div>
    <Nav v-bind:themeClass="themeClass" />
    <Header />
    <Main v-bind:isLight="isLight" v-bind:themeClass="themeClass" />
    <Footer v-bind:themeClass="themeClass" />
    <i
      class="theme-btn big icon"
      v-bind:class="modeIcon"
      v-on:click="theme()"
    ></i>
  </div>
</template>

<script>
import Nav from "./components/Nav.vue";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";
export default {
  name: "App",
  components: {
    Nav,
    Header,
    Main,
    Footer,
  },
  data() {
    return {
      isLight: true,
      themeClass: "light",
      modeIcon: "moon",
    };
  },
  methods: {
    theme() {
      this.isLight = !this.isLight;
      this.themeBtn();
      this.isLight ? (this.themeClass = "light") : (this.themeClass = "dark");
    },
    themeBtn() {
      this.isLight ? (this.modeIcon = "moon") : (this.modeIcon = "sun");
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Abel&display=swap");
@import url("https://fonts.googleapis.com/css?family=News+Cycle&display=swap");
/* VARIABLES DECLARATION */
:root {
  --primary: #ff6908;
  --secondary: #ea2348bf;
  --dark: #353535;
  --darker: #252525;
  --light: #c1c1c1;
  --lighter: #e0e0e0;
  --lightTransparence: #0000003b;
  --blue: #3396b5;
  --bluer: #607d8b;
  --yellow: #ffd100d6;
}
* {
  margin: 0;
  padding: 0;
  font-family: sans-serif;
  box-sizing: border-box;
  transition: all 0.8s ease-in-out;
}
html {
  scroll-behavior: smooth;
}
body {
  font-family: "Abel", sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI",
    "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans",
    "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
header h1,
header h2 {
  text-transform: uppercase;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Abel", sans-serif;
  margin: 1rem auto;
}
img {
  width: 100%;
  clear: both;
}
i {
  margin-right: 1rem;
}
ul {
  list-style: none;
}
hr {
  margin: 1rem 0;
}
section {
  margin: 56.8px auto;
}
.container {
  padding: 1.7rem;
}
.grid {
  display: grid;
  grid-gap: 1rem;
}
.flex {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}
.flex-row {
  flex-direction: row;
  justify-content: space-between;
}
.flex-column {
  flex-direction: column;
}
.headline {
  padding-bottom: 1rem;
  margin-bottom: 3rem;
  border-bottom: 1px solid var(--bluer);
  font-size: 1.2rem;
  font-weight: 600;
}
.gradient-light {
  background: linear-gradient(-45deg, var(--light) 70%, var(--dark) 30%);
}
.gradient-dark {
  background: linear-gradient(-45deg, var(--light) 30%, var(--dark) 0%);
}

.theme-btn {
  width: 38px;
  height: 38px;
  position: fixed;
  bottom: 2rem;
  right: 1rem;
  z-index: 1;
}
/* -------------------------------------- */
/* special classes */
.light {
  background-color: var(--light);
  color: var(--dark);
}
.lighter {
  background-color: var(--lighter);
  color: var(--dark);
}
.dark {
  background-color: var(--dark);
  color: var(--light);
}
.darker {
  background-color: var(--darker);
  color: var(--light);
}
i.icon.moon {
  color: #666666;
}
i.icon.sun {
  color: var(--yellow);
}
/* media queries */
@media screen and (min-width: 1171px) {
  section {
    width: 1124px;
    margin: auto;
  }
}
@media screen and (max-width: 768px) {
  section {
    margin: 1rem auto;
  }
  .container {
    padding: 1rem;
  }
}
@media screen and (max-width: 500px) {
  .headline {
    padding-bottom: 0.5rem;
    margin-bottom: 1rem;
  }
}
</style>
