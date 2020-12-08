<template>
  <div class="container">
    <div class="row">
      <div class="col-md-8 col-md-offset-2">
        <div class="panel panel-default">
          <div class="panel-heading"></div>
          <div class="panel-body">
            <table class="table">
              <thead>
              <tr>
                <th>Name</th>
                <th>Username</th>
                <th>Email</th>
              </tr>
              </thead>
              <tbody v-if="user">
              <tr >
                <td><input class="inputInfo" type="text" name="name" v-model="user.name" placeholder="name"></td>
                <td><input class="inputInfo" type="text" name="username" v-model="user.username" placeholder="username"></td>
                <td><input class="inputInfo" type="text" name="email" v-model="user.email" placeholder="name"></td>
              </tr>
              </tbody>
              <thead>
              <tr>
                <th>Street</th>
                <th>Suite</th>
                <th>City</th>
              </tr>
              </thead>
              <tbody v-if="user">
              <tr>
                <td><input class="inputInfo" type="text" name="Street" v-model="user.address.street" placeholder="street"></td>
                <td><input class="inputInfo" type="text" name="Suite" v-model="user.address.suite" placeholder="suite"></td>
                <td><input class="inputInfo" type="text" name="City" v-model="user.address.city" placeholder="city"></td>
              </tr>
              </tbody>
              <thead>
              <tr>
                <th>Zipcode</th>
                <th>Phone</th>
                <th>Website</th>
              </tr>
              </thead>
              <tbody v-if="user">
              <tr>
                <td><input class="inputInfo" type="text" name="Zipcode" v-model="user.address.zipcode" placeholder="zipcode"></td>
                <td><input class="inputInfo" type="text" name="Phone" v-model="user.phone" placeholder="phone"></td>
                <td><input class="inputInfo" type="text" name="Website" v-model="user.website" placeholder="website"></td>
              </tr>
              </tbody>
            </table>
            <button>Save</button>
            <button>Delete User</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "singleUser",
  data() {
    return {
      user: [],
    }
  },
  created() {
    let id = this.$route.params.id
    axios
        .get("https://jsonplaceholder.typicode.com/users/"+id)
        .then(response => {
          this.user = response.data;
          console.log( this.user);
        })
        .catch(err => {
          throw err;
        });
    console.log(this.user)
  }
}
</script>

<style scoped>
.table, td, th{
  margin-left: auto;
  margin-right: auto;
  border-collapse: collapse;
  border: 1px solid #8f9296;
}

th, td{
  width: 40%;
  padding-right: 5%;
  padding-bottom: 5%;
  text-align: left;
}
</style>