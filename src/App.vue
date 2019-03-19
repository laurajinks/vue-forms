<template>
  <div class="container">
    <form v-if="!formSubmitted">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->
          <FullName v-model="fullName"/>
          <label for="email">Email</label>
          <input type="text" id="email" v-model="email">
          <label for="password">Password</label>
          <input type="password" id="password" v-model="password">
          <div>
            <label for="Yes">
              <input type="radio" id="yes" value="Yes" v-model="storeData"> Yes
            </label>
            <label for="No">
              <input type="radio" id="no" value="No" v-model="storeData"> No
            </label>
          </div>
          <button type="submit" @click.prevent="submitForm">Submit</button>
          <!-- Exercise 2 -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->
          <!-- Exercise 3 -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
        </div>
      </div>
    </form>
    <hr>
    <div class="row" v-if="formSubmitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ fullName }}</p>
            <p>Mail: {{ email }}</p>
            <p>Password: {{ password }}</p>
            <p>Store in Database?: {{ storeData }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FullName from "./components/FullName";
export default {
  data() {
    return {
      fullName: "Laura Jimenez",
      email: "",
      password: "",
      storeData: "No",
      formSubmitted: false
    };
  },
  methods: {
    submitForm() {
      this.formSubmitted = true;
    }
  },
  components: {
    FullName
  }
};
</script>

<style>
</style>

