<template>
  <footer v-bind:class="themeClass">
    <div class="details grid" data-aos="zoom-in">
      <Infos />
      <ContactUs />
    </div>
    <p class="copyrights">
      Copyright &copy; 2020 |{{ ' ' }}
      <span> <span>Clothing </span>App </span>
    </p>
  </footer>
</template>
<script>
import Infos from './footer/Infos';
import ContactUs from './footer/ContactUs';
export default {
  name: 'Footer',
  components: {
    Infos,
    ContactUs,
  },
  props: {
    themeClass: String,
  },
};
</script>
<style scoped>
footer .details.grid {
  padding: 1rem;
  margin-bottom: 1rem;
  grid-template-columns: 3fr 1fr;
}
footer .copyrights {
  width: 100%;
  text-align: center;
  background: var(--lightTransparence);
  padding: 1rem;
}
footer span {
  text-transform: uppercase;
}
footer span span {
  color: var(--primary);
}
@media screen and (max-width: 768px) {
  footer .details.grid {
    grid-template-columns: 1fr;
  }
}
</style>
