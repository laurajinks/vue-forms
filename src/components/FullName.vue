<template>
  <div>
    <label for="firstName">First Name</label>
    <input type="text" id="firstName" :value="firstName" @input="nameChanged(true, $event)">
    <label for="lastName">Last Name</label>
    <input type="text" id="lastName" :value="lastName" @input="nameChanged(false, $event)">
  </div>
</template> 

<script>
export default {
  name: "FullName",
  props: ["value"],
  methods: {
    nameChanged(isFirst, event) {
      let name = "";
      if (isFirst) {
        name = event.target.value + " " + this.lastName;
      } else {
        name = this.firstName + " " + event.target.value;
      }
      this.$emit("input", name);
    }
  },
  computed: {
    firstName() {
      return this.value.split(" ")[0];
    },
    lastName() {
      return this.value.split(" ")[1];
    }
  }
};
</script>
