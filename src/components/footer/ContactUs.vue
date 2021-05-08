<template>
  <div id="contact-us" class="contact-us">
    <div data-aos="zoom-in">
      <h3>Contact Us</h3>
      <form @submit="handleSubmit">
        <label htmlFor="name">Full Name:</label>
        <input
          type="text"
          v-model="contact.name"
          placeholder="Full Name"
          required
        />
        <label htmlFor="email">E-Mail Address:</label>
        <input
          type="email"
          v-model="contact.email"
          placeholder="E-Mail Here"
          required
        />
        <label htmlFor="name">Message:</label>
        <textarea
          v-model="contact.message"
          placeholder="Message Here"
          required
        ></textarea>
        <input type="submit" value="Send Message" />
      </form>
    </div>
  </div>
</template>
<script>
export default {
  name: "ContactUs",
  data() {
    return {
      contact: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  methods: {
    handleSubmit: function(event) {
      event.preventDefault();
    },
  },
};
</script>
<style scoped>
.contact-us h3 {
  margin-bottom: 1.5rem;
}
.contact-us label {
  font-size: 0.9rem;
  text-align: left;
  margin-bottom: 5px;
}
.contact-us input,
.contact-us textarea {
  width: 100%;
  color: var(--lighter);
  background: var(--lightTransparence);
  padding: 0.5rem;
  margin-bottom: 0.5rem;
  border: none;
  border-radius: 5px;
}
.contact-us input:focus,
.contact-us textarea:focus {
  outline: none;
}
.contact-us input[type="submit"] {
  background: var(--primary);
  font-weight: bold;
}
</style>
