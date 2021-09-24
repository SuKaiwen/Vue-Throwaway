<template>
  <div class="container">
    <h1>Identity Generator</h1>
    <br />
    <div class="card">
      <div class="image-grid">
        <img src="@/assets/backgroundd.jpg" class="image-background"/>
        <img v-bind:src="image" class="image-circle" alt="image" />
        
      </div>
      <h1>{{firstName}} {{lastName}}</h1>
      <h5>Gender: {{gender}} </h5>
      <h5>Email: {{email}}</h5>
      <h5>Username: {{username}}</h5>
      <h5>Phone Number: {{cell}}</h5>
      <h5>Password: {{password}}</h5>
      <div class="container">
        <button v-on:click="generateUser">Generate User</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    firstName: String,
    lastName: String,
    email: String,
    username: String,
    password: String,
    gender: String,
    cell: String,
    image: String,
  },

  methods: {
    generateUser(){
      this.$parent.generateUser();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="../CSS/app.css" scoped>

</style>
