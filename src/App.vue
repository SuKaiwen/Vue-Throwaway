<template>
  <Body 
    :firstName = "user.firstName"
    :lastName = "user.lastName"
    :email = "user.email"
    :username = "user.username"
    :password = "user.password"
    :gender = "user.gender"
    :cell = "user.cell"
    :image = "user.image"
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
        cell: '123-456-7890',
        image: 'https://randomuser.me/api/portraits/men/49.jpg',
      }
    }
  },

  methods: {
    async generateUser(){
      const res = await fetch('https://randomuser.me/api')
      const {results} = await res.json()
      this.user.firstName = results[0].name.first
      this.user.lastName = results[0].name.last
      this.user.email = results[0].email
      this.user.gender = results[0].gender
      this.user.cell = results[0].cell
      this.user.username = results[0].name.first + results[0].name.last + Math.ceil(Math.random()*1000)
      this.user.password = Math.random().toString(36).substring(2, 15) + Math.random().toString(36).substring(2, 15);
      this.user.image = results[0].picture.large
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
