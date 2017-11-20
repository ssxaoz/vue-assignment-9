<template>
    <div class="container">
        <form v-if="!isSubmitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->
                    <h1>Signup Form</h1>
                    <hr>
                    <app-full-name v-model="userData"></app-full-name>

                    <div class="form-group">
                      <label for="email">Mail</label>
                      <input
                        type="text"
                        id="email"
                        class="form-control"
                        v-model="userData.email"
                      >
                    </div>
                    <div class="form-group">
                      <label for="password">Password</label>
                      <input
                        type="password"
                        id="password"
                        class="form-control"
                        v-model.lazy="userData.password"
                      >
                    </div>
                    <hr>
                    <div class="row">
                      <div class="col-xs-12 col-sm-8 col-md-6 col-md-offset-3 form-group">
                        Store Data?
                        <label for="storeYes">
                          <input
                            type="radio"
                            id="storeYes"
                            value="Yes"
                            v-model="isStore"
                          > Yes
                        </label>
                        <label for="storeNo">
                          <input
                            type="radio"
                            id="storeNo"
                            value="No"
                            v-model="isStore"
                          > No
                        </label>
                      </div>
                    </div>
                    <div class="row">
                      <div class="col-xs-12 col-sm-8 col-md-6 col-md-offset-3">
                        <button
                          class="btn btn-primary"
                          @click.prevent="submitted"
                        >Submit!
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
        <div class="row" v-else>
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                      <p><b>Full Name:</b> {{ fullName }}</p>
                        <p><b>Mail:</b> {{ userData.email }}</p>
                        <p><b>Password:</b> {{ userData.password }}</p>
                        <p><b>Store in Database?:</b> {{ isStore }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName from './FullName.vue'

    export default {
      data: function () {
        return {
          userData: {
            firstName:'',
            lastName:'',
            email:'',
            password:''
          },
          isStore: 'Yes',
          isSubmitted: false
        }
      },
      computed: {
        fullName: function() {
          return this.userData.firstName + ' ' + this.userData.lastName;
        }
      },
      methods: {
        submitted() {
          this.isSubmitted = true;
        }
      },
      components: {
        appFullName: FullName
      }
    }
</script>

<style>
</style>
