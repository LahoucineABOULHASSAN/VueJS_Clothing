<template>
  <section v-if="products.length" id="our-products" data-aos="flip-right">
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
  <Loading v-else-if="!error" />
  <Error v-if="error" :error="error" />
</template>
<script>
import Axios from "axios";
import Product from "./Product";
import Loading from "../Loading";
import Error from "../Error";
export default {
  name: "Products",
  components: {
    Product,
    Loading,
    Error,
  },
  props: {
    isLight: Boolean,
  },
  data() {
    return {
      products: [],
      error: null,
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const url =
        "https://raw.githubusercontent.com/LahoucineABOULHASSAN/json_files/main/products.json";
      try {
        const res = await Axios.get(url);
        if (res.status !== 200) {
          throw Error("Couldn't get res");
        }
        this.products = res.data;
      } catch (err) {
        this.error = err.message;
      }
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
