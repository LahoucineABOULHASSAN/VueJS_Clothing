<template>
  <div>
    <img v-bind:src="product.image" v-bind:alt="product" />
    <div v-bind:class="theme()">
      <p>
        <span class="product-name">{{ product.product }}</span>
        <span class="product-price">${{ product.price }}</span>
      </p>
      <p class="product-desc text-secondary">{{ product.description }}</p>
      <p>
        <span class="product-reviews">Reviews({{ product.reviews }})</span>
        <span class="product-rating">
          <Rating v-bind:key="product.id" v-bind:rating="product.rating" />
        </span>
      </p>
    </div>
  </div>
</template>
<script>
import Rating from './Rating';
export default {
  name: 'Product',
  components: {
    Rating,
  },
  props: {
    isLight: Boolean,
    product: Object,
  },
  methods: {
    theme: function() {
      return this.isLight ? 'light details' : 'darker details';
    },
  },
};
</script>
<style scoped>
img {
  height: 200px;
  display: block;
}
.details {
  line-height: 1.3rem;
  font-weight: 500;
  padding: 1rem;
}
p,
span {
  padding-bottom: 1rem;
}
.product-name {
  color: var(--blue);
  float: left;
}
.product-price {
  float: right;
}
.product-desc {
  clear: both;
  font-weight: 300;
  text-align: justify;
}
.product-reviews {
  color: var(--primary);
  float: left;
}
.product-rating {
  color: var(--primary);
  float: right;
}
</style>
