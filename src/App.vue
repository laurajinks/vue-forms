<template>
  <div class="container">
    <form>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->
          <form>
            <label for="fullName">Full Name</label>
            <input type="text" id="fullName" v-model="userData.fullName">
            <label for="email">Email</label>
            <input type="text" id="email" v-model="userData.email">
            <label for="password">Password</label>
            <input type="password" id="password" v-model="userData.password">
            <div>
              <label for="Yes">
                <input type="radio" id="yes" value="Yes" v-model="storeData"> Yes
              </label>
              <label for="No">
                <input type="radio" id="no" value="No" v-model="storeData"> No
              </label>
            </div>
          </form>
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
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ userData.fullName }}</p>
            <p>Mail: {{ userData.email }}</p>
            <p>Password: {{ userData.password }}</p>
            <p>Store in Database?: {{ storeData }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userData: {
        fullName: "",
        email: "",
        password: ""
      },
      storeData: "No"
    };
  }
};
</script>

<style>
</style>

