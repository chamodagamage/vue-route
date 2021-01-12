<template>
  <h1> Current Jobs</h1>
  <div v-for="job in jobs" :key="job.id" class='jobs'>
      <router-link :to='{name:"JobDetails", params:{id:job.id}}'><h2>{{job.title}}</h2></router-link>
  </div>
</template>

<script>
export default {
 data(){
     return(
         {
             jobs:[
                 {title:'Web Developer', id:1 , discription: 'lorem'},
                 {title:'Web Designer', id:2 , discription: 'lorem'},
                 {title:'UX designer', id:3 , discription: 'lorem'}
             ]
         }
     )
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
</style>