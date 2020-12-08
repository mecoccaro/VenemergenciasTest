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
                <td><input id="name" class="inputInfo" type="text" name="name" v-model="form.newname" placeholder="new name"></td>
                <td><input class="inputInfo" type="text" name="username" v-model="form.newusername" placeholder="new username"></td>
                <td><input class="inputInfo" type="text" name="email" v-model="form.newemail" placeholder="new name"></td>
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
                <td><input class="inputInfo" type="text" name="Street" v-model="form.newstreet" placeholder="new street"></td>
                <td><input class="inputInfo" type="text" name="Suite" v-model="form.newsuite" placeholder="new suite"></td>
                <td><input class="inputInfo" type="text" name="City" v-model="form.newcity" placeholder="new city"></td>
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
                <td><input class="inputInfo" type="text" name="Zipcode" v-model="form.newzipcode" placeholder="new zipcode"></td>
                <td><input class="inputInfo" type="text" name="Phone" v-model="form.newphone" placeholder=" new phone"></td>
                <td><input class="inputInfo" type="text" name="Website" v-model="form.newwebsite" placeholder="new website"></td>
              </tr>
              </tbody>
            </table>
            <button v-on:click="submitChange">Save</button>
            <button v-on:click="deleteRequest">Delete User</button>
          </div>
          <div class="success" v-if="resp">
            <p v-for="res in resp" :key="res.id">
              {{res}}
            </p>
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
      user: [],
      form: {
        newname: '',
        newusername: '',
        newemail: '',
        newaddress: [{
          newstreet: '',
          newsuite: '',
          newcity: '',
          newzipcode: '',
        }],
        newphone: '',
        newwebsite: '',
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
      axios
      .put('https://jsonplaceholder.typicode.com/users/'+this.$route.params.id,this.form)
      .then((res)=> {
        this.resp = res.data
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