<template>
<div v-if="job">
  <h1>{{job.title}}</h1>
  <p>job id is {{id}}</p>
  <p>{{job.discription}}</p>
</div>
<div v-else> Loading.....</div>

</template>

<script>
export default {
  props:['id'],
 data(){
     return({
        //  id: this.$route.params.id
        job:null
     })
 },
  mounted(){
      fetch('http://localhost:3000/jobs/'+this.id).then(res => res.json())
      .then(data => this.job = data)
  }
}
</script>

<style>

</style>