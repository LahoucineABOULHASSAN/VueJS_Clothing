<template>
  <section id="our-products" data-aos="flip-right">
    <p class="headline">
      Latest Products
      <span>
        <a href="#home">
          VIEW ALL PRODUCTS <i class="chevron right icon"></i>
        </a>
      </span>
    </p>
    <div class="grid">
      <Product
        v-for="product in products"
        v-bind:key="product.id"
        v-bind:product="product"
        v-bind:isLight="isLight"
      />
    </div>
  </section>
</template>
<script>
import Axios from 'axios';
import Product from './Product';
export default {
  name: 'Products',
  components: {
    Product,
  },
  props: {
    isLight: Boolean,
  },
  data() {
    return {
      products: [],
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const url =
        'https://raw.githubusercontent.com/LahoucineABOULHASSAN/json_files/main/products.json';
      const res = await Axios.get(url);
      this.products = res.data;
    },
  },
};
</script>
<style scoped>
.grid {
  grid-template-columns: repeat(4, 1fr);
}
.headline span {
  float: right;
}
.headline span a {
  color: var(--primary);
  font-size: 0.8rem;
  text-decoration: none;
}
/* Media Queries */
@media screen and (max-width: 768px) {
  .grid {
    grid-template-columns: 1fr 1fr;
  }
  div .details .product-reviews,
  div .details .product-rating {
    font-size: 0.9rem;
  }
}
@media screen and (max-width: 500px) {
  .grid {
    grid-template-columns: 1fr;
  }
  div img {
    height: auto;
  }
}
</style>
