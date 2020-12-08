<template>
  <div class="container">
    <div class="row">
      <div class="col-md-8 col-md-offset-2">
        <div class="panel panel-default">
          <div class="panel-heading">List of users</div>
          <div class="panel-body">
            <table class="table">
              <thead>
              <tr>
                <th>Name</th>
                <th>Email</th>
              </tr>
              </thead>
              <tbody v-if="users">
              <tr v-for="user in users" :key="user.id">
                <td>{{ user.name }}</td>
                <td>{{ user.email }}</td>
                <td><button><router-link :to="{name: '/user/:id', id: user.id}"><strong>+</strong></router-link></button></td>
              </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'allUsers',
  data() {
    return {
      users: [],
    }
  },
  mounted() {
    axios
        .get("https://jsonplaceholder.typicode.com/users")
        .then(response => {
          this.users = response.data;
          console.log(this.results);
        })
        .catch(err => {
          throw err;
        });
  }
}
</script>

<style scoped>
.table, td, th{
  margin-left: auto;
  margin-right: auto;
  border-collapse: collapse;
  border: 1px solid black
}

th, td{
  width: 40%;
  padding: 10px;
  text-align: left;
}
</style>