<template>
  <section id="about-us" data-aos="flip-left">
    <p class="headline">About Clothing App</p>
    <div class="grid">
      <div>
        <h3 class="info">Looking for the best products?</h3>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Natus
          aperiam nisi id, fuga aut laborum tempore saepe dicta ducimus placeat
        </p>
        <ul>
          <li>Lorem, ipsum dolor sit.</li>
          <li>Lorem, ipsum dolor sit.</li>
          <li>Lorem, ipsum dolor sit.</li>
        </ul>
        <button>{{ 'Read More' }} <i class="chevron right icon"></i></button>
      </div>
      <figure>
        <img
          src="https://images.unsplash.com/photo-1542744173-05336fcc7ad4?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1382&q=80"
          alt="marketing pic from unsplash"
        />
      </figure>
    </div>
  </section>
</template>
<script>
export default {
  name: 'About',
};
</script>
<style scoped>
/* Custom Style */
#about-us .grid {
  line-height: 1.6;
  grid-template-columns: 1fr 1fr;
  padding-bottom: 1rem;
  border-bottom: 1px solid var(--bluer);
}
#about-us .grid h3 {
  color: var(--blue);
  font-size: 1.1rem;
  font-weight: 500;
  margin-bottom: 1rem;
}
#about-us .grid p {
  font-size: 0.9rem;
  margin-bottom: 1rem;
}
#about-us .grid ul {
  font-size: 0.9rem;
  list-style: circle inside;
  margin-bottom: 1rem;
}
#about-us .grid div button {
  font-size: 0.9rem;
  color: var(--lighter);
  padding: 0.7rem 1rem;
  background: var(--primary);
  border: none;
  border-radius: 5px;
}

/* Media Queries */
@media screen and (max-width: 500px) {
  #about-us .grid {
    grid-template-columns: 1fr;
  }
  #about-us .headline {
    font-size: 1rem;
  }
}
</style>
