<template>
<div class="form-conteiner">
  <h2>Messege {{ message }}</h2>
  <form @submit.prevent="submitForm">
     <label for="name">Name</label>
     <input type="text" id="name" v-model="name">
     <label for="email">Email</label>
     <input type="email" id="email" v-model="email">
     <button type="submit">Submit</button>
  </form>

  <ul v-if="submissions.length > 0">
  <li v-for="(submissions, index) in submissions" :key="index">
  <p>Name:{{ submissions.name }}</p>
  <p>Email:{{ submissions.email }}</p>
  </li>
  </ul>
</div>
</template>

<script>



export default  {
  data(){
return{
  name:'',
  email:'',
  submissions:[]
};
},
methods:{
  submitForm(){
    const newSubmissons = {
      name: this.name,
      email: this.email,
    }
    this.submissions.push(newSubmissons)
    this.name = ''
    this.email = ''
  },
  showMessage(){
    alert("hello")
  }
},
computed:{
  message(){
    const count = this.submissions.length;
    if (count=== 0 ){
      return "No submissions Yet"
    } else if (count === 1){
      return " 1 Submissions!"
    } else {
      return `${count} Submissions`
    }
  }
}

}
</script>

<style>

</style>
