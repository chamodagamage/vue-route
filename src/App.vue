<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link :to="{name:'About'}">About</router-link> |
    <router-link :to="{name:'Jobs'}">Jobs</router-link>
  </div>
  <button @click="redirect">Redirect</button>
  <button @click="backword">Go Backword</button>
  <button @click="forword">Go Forword</button>
  <router-view/>
</template>

<script>
export default {
  methods:{
    redirect(){
       this.$router.push({name:"About"})
    },
    backword(){
      this.$router.go(-1)
    },
    forword(){
       this.$router.go(1)
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
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  margin: 0 10px;
}

#nav a.router-link-exact-active {
  color: #f3f5f4;
  background-color: crimson;
  border-radius: 5px;
  padding: 10px;
}
button{
  margin: 10px 5px;
  border:none;
  padding: 10px 20px;
  border-radius: 10px;
  cursor: pointer;
}
</style>
