<template>
  <div>
    <i
      v-for="i in 5"
      v-bind:key="i"
      v-bind:class="handleRate(i)"
      class="star small icon"
    ></i>
  </div>
</template>
<script>
  export default {
    name: 'Rating',
    props: {
      rating: Number,
    },
    methods: {
      handleRate: function(i) {
        if (i <= this.rating) {
          return 'fitted'
        } else {
          return 'outline fitted'
        }
      },
    },
  }
</script>
