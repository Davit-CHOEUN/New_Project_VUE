<template>
  <div class="container">
    <div class="left-box">
      <div class="header">
        <img src="../assets/logo.png" alt="" />
        <!-- <h1>Register</h1> -->
      </div>
      <div class="form-group">
        <input
          type="text"
          class="controls"
          placeholder="Enter Name"
          v-model="name"
        />
       
      </div>
      <div class="form-group">
        <input
          type="number"
          class="controls"
          placeholder="Enter Age"
          v-model="age"
        />
      </div>
      <div class="form-group">
        <input
          type="password"
          class="controls"
          placeholder="Enter Password"
          v-model="password"
        />
      </div>
      <div class="form-group">
        <input
          type="email"
          class="controls"
          placeholder="Enter email"
          v-model="email"
        />
      </div>
      <div class="form-group">
        <input
          type="number"
          class="controls"
          placeholder="Enter phone number"
          v-model="phone"
        />
      </div>
      <button type="button" @click="submit()">Submit</button>
    </div>
    <div class="right-box">
        <h3 class="text-danger" v-if="list.lenght==0">No data</h3>
        <h3 class="text-success" v-else>Here is data</h3>
      <table class="table">
        <thead>
          <th scope="col">Name</th>
          <th scope="col">Age</th>
          <th scope="col">Password</th>
          <th scope="col">Email</th>
          <th scope="col">Phone</th>
        </thead>
        <tbody>
          <tr v-for="lists in list" :key="lists">
            <td scope="row">{{ lists.name }}</td>
            <td>{{ lists.age }}</td>
            <td>{{ lists.password }}</td>
            <td>{{ lists.email }}</td>
            <td>{{ lists.phone }}</td>
            <td> <button class="btn btn-danger" @click="deleteData(index)">Delete</button></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
  
  <script>
export default {
  data() {
    return {
      allList: "",
      list: [
        {
          name: "Davit",
          age: 28,
          email: "pnc@.com",
          phone: "23456765432",
          password: "234564",
        },
        {
          name: "Davit",
          age: 28,
          email: "pnc@.com",
          phone: "23456765432",
          password: "234564",
        },
      ],
    };
  },
  methods: {
    submit() {
        this.list.push({
          name: this.name,
          age: this.age,
          email: this.email,
          phone: this.phone,
          password: this.password,
        });
        console.log(this.list);
    },
    deleteData(index){
        this.list.splice(index, 1);
    }
  },
  computed: {
    name() {
      return this.list.name;
    },
    age() {
      return this.list.age;
    },
    email() {
      return this.list.email;
    },
    phone() {
      return this.list.phone;
    },
    password() {
      return this.list.password;
    },
  },
};
</script>
  <style>
.container {
  display: flex;
  justify-content: center;
}
.left-box {
  border: 2px solid orange;
  padding: 10px;
}
.right-box {
  border: 2px solid teal;
  padding: 10px;
  width: 100%;
}
.form-group {
  margin-bottom: 10px;
  display: flex;
  flex-direction: column;
  text-align: left;
}
label {
  padding-bottom: 10px;
}
.controls {
  padding: 10px;
  width: 500px;
  box-sizing: border-box;
}
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  text-align: left;
}
ul .info {
  padding: 10px;
  margin-bottom: 10px;
  border-bottom: 1px solid #ccc;
}
</style>