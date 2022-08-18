<template>
  <form>
    <div>
      <label>Name</label>
      <input v-model="name" type="text" placeholder="Name" />
    </div>
    <div>
      <label>Phone:</label>
      <input
        v-model="phoneNumber"
        type="tel"
        placeholder="Phone Number"
        required
      />
    </div>
    <div>
      <label>Email</label>
      <input
        v-model="emailAddress"
        type="email"
        placeholder="Email Address"
        required
      />
    </div>
    <button @click.prevent="formSubmit" type="submit">Add Contact</button>
  </form>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      name: "",
      phoneNumber: "",
      emailAddress: "",
    };
  },
  emits: ["newfriend"],
  methods: {
    formSubmit() {
      this.$emit("newfriend", {
        name: this.name,
        phone: this.phoneNumber,
        email: this.emailAddress,
      });
    },
  },
};
</script>
