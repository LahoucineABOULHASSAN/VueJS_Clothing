<template>
  <div id="useful-links" class="footer-infos grid">
    <div data-aos="zoom-in">
      <h3>Finance Business</h3>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste dolorem
        tenetur nesciunt est non ullam?
      </p>
      <ul class="icons">
        <li class="icon-item">
          <i class="twitter large icon"></i>
        </li>
        <li class="icon-item">
          <i class="linkedin large icon"></i>
        </li>
        <li class="icon-item">
          <i class="facebook large icon"></i>
        </li>
        <li class="icon-item">
          <i class="telegram large icon"></i>
        </li>
      </ul>
    </div>
    <div data-aos="zoom-in">
      <h3>Useful Links</h3>
      <ul>
        <li>Lorem ipsum dolor</li>
        <li>Lorem ipsum dolor</li>
        <li>Lorem ipsum dolor</li>
        <li>Lorem ipsum dolor</li>
      </ul>
    </div>
    <div data-aos="zoom-in">
      <h3>Additional Pages</h3>
      <ul>
        <li>About Us</li>
        <li>How We Work</li>
        <li>Contact Us</li>
        <li>Privacy and Policy</li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: "Infos",
};
</script>
<style scoped>
.footer-infos.grid {
  text-align: left;
  grid-template-columns: repeat(3, 1fr);
}
.footer-infos h3 {
  margin-bottom: 1.5rem;
}
.footer-infos li {
  margin-bottom: 0.8rem;
  cursor: pointer;
}
.footer-infos li:hover {
  color: var(--primary);
}
.footer-infos ul.icons {
  margin-top: 1rem;
}
.footer-infos li.icon-item {
  display: inline-block;
  color: var(--primary);
}
/* Media Queries */
@media screen and (max-width: 500px) {
  .footer-infos.grid {
    grid-template-columns: 1fr;
    text-align: center;
  }
}
</style>
