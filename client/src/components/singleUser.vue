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
                <th>Name: {{user.name}}</th>
                <th>Username: {{user.username}}</th>
                <th>Email: {{user.email}}</th>
              </tr>
              </thead>
              <tbody v-if="user">
              <tr >
                <td><input id="name" class="inputInfo" type="text" name="name" v-model="form.name" placeholder="new name"></td>
                <td><input class="inputInfo" type="text" name="username" v-model="form.username" placeholder="new username"></td>
                <td><input class="inputInfo" type="text" name="email" v-model="form.email" placeholder="new name"></td>
              </tr>
              </tbody>
              <thead>
              <tr>
                <th>Street: {{user.address.street}}</th>
                <th>Suite: {{user.address.suite}}</th>
                <th>City: {{user.address.city}}</th>
              </tr>
              </thead>
              <tbody v-if="user">
              <tr>
                <td><input class="inputInfo" type="text" name="Street" v-model="form.street" placeholder="new street"></td>
                <td><input class="inputInfo" type="text" name="Suite" v-model="form.suite" placeholder="new suite"></td>
                <td><input class="inputInfo" type="text" name="City" v-model="form.city" placeholder="new city"></td>
              </tr>
              </tbody>
              <thead>
              <tr>
                <th>Zipcode: {{user.address.zipcode}}</th>
                <th>Phone: {{user.phone}}</th>
                <th>Website: {{user.website}}</th>
              </tr>
              </thead>
              <tbody v-if="user">
              <tr>
                <td><input class="inputInfo" type="text" name="Zipcode" v-model="form.zipcode" placeholder="new zipcode"></td>
                <td><input class="inputInfo" type="text" name="Phone" v-model="form.phone" placeholder=" new phone"></td>
                <td><input class="inputInfo" type="text" name="Website" v-model="form.website" placeholder="new website"></td>
              </tr>
              </tbody>
            </table>
            <button v-on:click="submitChange">Save</button>
            <button v-on:click="deleteRequest">Delete User</button>
          </div>
          <div class="success" v-if="resp">
            <h3 v-if="msg2">User updated</h3>
            <p v-for="(key,res) in resp" :key="res.name">
               {{res}}: {{key}}
            </p>
            <button class="btn btn-small btn-brand" v-on:click="hideAlert()">Close</button>
          </div>
          <div v-if="msg" class="alert">
            <p class="text-brand m-20">
              {{msg}}
              <button class="btn btn-small btn-brand" v-on:click="hideAlert()">Close</button>
            </p>
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
      msg: '',
      msg2: null,
      user: [],
      form: {
        name: null,
        username: null,
        email: null,
        address: {
          street: null,
          suite: null,
          city: null,
          zipcode: null,
        },
        phone: null,
        website: null,
      },
      resp: [],
    }
  },
  created() {
    let id = this.$route.params.id
    axios
        .get("https://jsonplaceholder.typicode.com/users/"+id)
        .then(response => {
          this.user = response.data;
        })
        .catch(err => {
          throw err;
        });
  },
  methods: {

    submitChange(){
      if (this.form.name == null || this.form.username == null || this.form.email == null){
        this.msg2 = 'No changes'
        return ;
      }
      axios
      .put('https://jsonplaceholder.typicode.com/users/'+this.$route.params.id,this.form)
      .then((res)=> {
        this.resp = res.data
        this.msg2 = 'User Updated'
      })
      .catch((error)=> {
        throw error
      });

    },
    deleteRequest(){
      axios
      .delete('https://jsonplaceholder.typicode.com/users/'+this.$route.params.id)
      .then((res)=> {
        this.msg = 'User eliminated'
        this.resp = res.data
      })
      .catch((error)=> {
        throw error
      });

    },
    hideAlert(){
      this.$router.push('/principal')
    }
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

  text-align: left;
}
</style>