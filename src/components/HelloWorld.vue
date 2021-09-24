<template>
  <div class="container">
    <h1>Account Generator</h1>
    <br />
    <div class="card">
      <h5>Email: </h5>
      <h5>Username: </h5>
      <h5>Password: </h5>
      <div class="container">
        <button>Generate User</button>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="../CSS/app.css" scoped>

</style>
