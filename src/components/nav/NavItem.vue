<template>
  <a
    :class="link.link === '#home' ? themeClass + ' active' : themeClass"
    class="nav-item light"
    v-bind:href="link.link"
    v-on:click="isActive"
  >
    {{ link.value }}
  </a>
</template>
<script>
  export default {
    name: 'NavItem',
    props: {
      link: Object,
      themeClass: String,
    },
    methods: {
      isActive: function(event) {
        const navLinks = document.querySelectorAll('.nav-item')
        console.log(navLinks)
        navLinks.forEach((elem) => {
          if (elem === event.target) {
            event.target.classList.add('active')
          } else elem.classList.remove('active')
        })
      },
    },
  }
</script>
<style scoped>
  .nav-item {
    float: left;
    cursor: pointer;
    background: none;
    text-align: center;
    text-decoration: none;
    font-weight: 600;
    font-family: 'News Cycle', sans-serif;
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
