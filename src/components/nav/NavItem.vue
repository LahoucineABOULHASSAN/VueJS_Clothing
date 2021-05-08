<template>
  <span
    :data-id="link.link"
    :class="link.link === '#home' ? themeClass + ' active' : themeClass"
    class="nav-item light"
    v-on:click="isActive"
  >
    {{ link.value }}
  </span>
</template>
<script>
import { isActive } from "../../utilities/nav";
export default {
  name: "NavItem",
  props: {
    link: Object,
    themeClass: String,
  },
  data() {
    return { isActive };
  },
};
</script>
<style scoped>
.nav-item {
  float: left;
  cursor: pointer;
  background: none;
  text-align: center;
  text-decoration: none;
  font-weight: 600;
  font-family: "News Cycle", sans-serif;
  padding: 0.8rem;
}
.nav-item:hover {
  color: var(--primary);
}
.nav-item:focus {
  outline: none;
}
.nav-item:visited {
  color: inherit;
}
.nav-item.active {
  border-bottom: 4px solid var(--primary);
}
</style>
