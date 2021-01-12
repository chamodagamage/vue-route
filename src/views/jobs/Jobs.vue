<template>
  <h1> Current Jobs</h1>
  <div v-if="jobs.length">
    <div v-for="job in jobs" :key="job.id" class='jobs'>
        <router-link :to='{name:"JobDetails", params:{id:job.id}}'><h2>{{job.title}}</h2></router-link>
    </div>
  </div>
  <div v-else> Loading......</div>
</template>

<script>
export default {
 data(){
     return(
         {
             jobs:[]
         }
     )
 },
 mounted(){
     fetch('http://localhost:3000/jobs').then(res => res.json())
       .then(data => this.jobs = data)
       .catch(err => console.log(err.message))
 }
}
</script>

<style>
.jobs{
    width: 40%;
    margin:5px auto;
    background-color: rgb(228, 227, 227);
    padding: 10px 30px;
    border-radius: 20px;
    cursor: pointer;
}
.jobs h2{
    color: black;
}
.jobs a{
    text-decoration: none;
}
.jobs:hover{
    background-color: rgb(187, 184, 184);;
}
</style>