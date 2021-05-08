<template>
  <nav>
    <div v-bind:class="themeClass" class="topnav" id="myTopnav">
      <div class="logo" @click="scrollTo('#home')">
        <span>clothing </span>App
      </div>
      <div class="menu">
        <NavItem
          v-for="link in links"
          v-bind:key="link.link"
          v-bind:link="link"
          v-bind:themeClass="themeClass"
        />
        <div class="navBtn" v-on:click="displayMenu">
          <i class="bars icon responsive-btn"></i>
        </div>
      </div>
    </div>
  </nav>
</template>
<script>
import NavItem from "./nav/NavItem";
import { displayMenu, scrollTo } from "../utilities/nav";
export default {
  name: "Nav",
  components: {
    NavItem,
  },
  props: {
    themeClass: String,
  },
  data() {
    return {
      links: [
        { link: "#our-products", value: "products" },
        { link: "#useful-links", value: "useful links" },
        { link: "#about-us", value: "about us" },
        { link: "#contact-us", value: "contact us" },
      ],
      displayMenu,
      scrollTo,
    };
  },
};
</script>

<style scoped>
/* Custom Style */
nav {
  color: var(--light);
  padding: 0 1rem;
}
.topnav {
  width: 100%;
  height: 56.8px;
  text-transform: uppercase;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 2;
  overflow: hidden;
}
.menu {
  float: right;
  text-transform: capitalize;
}
.logo {
  float: left;
  cursor: pointer;
  font-size: 1.2rem;
  font-weight: 600;
  padding: 0.9rem;
}
.logo span {
  color: var(--primary);
}
.navBtn {
  display: none;
}
.navBtn:hover {
  background: none;
  color: var(--primary);
}
/* Screen styles */
@media screen and (max-width: 768px) {
  .topnav {
    padding-top: 0.5rem;
  }
  .topnav .logo {
    text-align: center;
    padding: 0.7rem;
    float: none;
  }
  .topnav .navBtn {
    display: block;
    position: absolute;
    right: 0;
    top: 0.35rem;
    padding: 0.9rem;
  }
  .topnav .menu .nav-item:hover {
    border: none;
  }
  .responsive .menu .nav-item {
    float: none;
    display: block;
    text-align: left;
  }
  .responsive {
    height: auto;
    z-index: 2;
  }
  .responsive .menu {
    float: none;
  }
  .responsive .active {
    border: none;
    background: var(--lightTransparence);
    color: var(--primary);
  }
}
</style>
