<template>
  <h1 v-if="job">{{job.title}}</h1>
  <p>THe job id is {{ id }}</p>
</template>

<script>
export default {
    props:['id'],
    data(){
      return{
        job:null
      }
    },
    mounted(){
      fetch('http://localhost:3000/jobs/'+this.id)
      .then((res)=>res.json())
      .then((data)=>this.job=data)
      .catch(err=>console.log(err.message))
    }

}
</script>

<style>

</style>