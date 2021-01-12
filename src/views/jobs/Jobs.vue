<template>
  <h1> Current Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
      <router-link :to='{name:"JobDetails", params:{id:job.id}}'>{{job.title}}</router-link>
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

</style>