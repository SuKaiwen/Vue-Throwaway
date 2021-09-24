<template>
  <Body 
    :firstName = "user.firstName"
    :lastName = "user.lastName"
    :email = "user.email"
    :username = "user.username"
    :password = "user.password"
    :gender = "user.gender"
    :cell = "user.cell"
    :function = "generateUser()"
  />
</template>

<script>
import Body from './components/Body.vue'

export default {
  name: 'App',
  components: {
    Body
  },

  data(){
    return{
      user: {
        firstName: 'John',
        lastName: 'Smith',
        email: 'JohnSmith@gmail.com',
        username: 'JohnSmith1234',
        password: 'abcdefg',
        gender: 'Male',
        cell: '123-456-7890'
      }
    }
  },

  methods: {
    async generateUser(){
      const res = await fetch('https://randomuser.me/api')
      const {results} = await res.json()
      console.log(results)
    }
  } 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  align-items:center;
  margin:auto;
  display:flex;
  flex-direction:column;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
