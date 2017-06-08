<template>
<div class="container">
  <form>
    <div class="row" v-if="!formSubmitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <!-- Exercise 1 -->
        <!-- Create a Signup Form where you retrieve the following Information -->
        <!-- Full Name (First Name + Last Name) -->
        <!-- Mail -->
        <!-- Password -->
        <!-- Store Data? Yes/No -->
        <!-- <div class="form-group">
          <label for="fullName">Full Name</label>
          <input type="text" class="form-control" id="fullName" v-model="name">
        </div> -->
        <full-name v-model="fullNameText"></full-name>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" class="form-control" id="email" v-model="email">
        </div>
        <div class="form-group">
          <label for="password">Password</label>
          <input type="password" class="form-control" id="password" v-model="password">
        </div>
        <div class="form-group">
          <span class="storeDataLabel">Store data?</span>
          <br>
          <label for="yesSwitch" id="yesLabel">
            <input type="radio" id="yesSwitch" value="yes" v-model="yesNoControl"> Yes
          </label>
          <label for="noSwitch">
            <input type="radio" id="noSwitch" value="no" v-model="yesNoControl"> No
          </label>
          <div>
            <button @click.prevent="submitForm" class="btn btn-primary">
              Submit Form
            </button>
          </div>
        </div>
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
          <p>Full Name: {{ fullNameText }}</p>
          <p>Mail: {{ email }}</p>
          <p>Password: {{ password }}</p>
          <p>Store in Database?: {{ yesNoControl }}</p>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import FullName from './FullName.vue';
export default {
  components: {
    fullName: FullName
  },
  data() {
    return {
      fullNameText: 'test test',
      email: '',
      password: '',
      yesNoControl: 'yes',
      formSubmitted: false
    }
  },
  methods: {
    submitForm() {
      this.formSubmitted = true;
    }
  }
}
</script>

<style scoped>
  form {
    margin-top: 20px;
  }

  #yesLabel {
    margin-right: 10px;
  }

  .storeDataLabel {
    display: inline-block;
    padding-bottom: 5px;
  }
</style>
