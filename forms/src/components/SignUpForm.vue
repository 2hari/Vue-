<template>
  <form>
    <label>Email:</label>
    <input type="email" required v-model="email">
    <label>Password:</label>
    <input type="password" required v-model="password">
    <label>Role:</label>
    <select v-model="role">
      <option value="developer">Web Developer</option>
      <option value="designer">Web Designer</option>
    </select>
    <label >accept terms and conditions</label>
    <input type="checkbox" v-model="terms" required>
    <label >shaun</label>
    <input value="shaun" type="checkbox" v-model="names"  >
    <label >yoshi</label>
    <input value="yoshi" type="checkbox" v-model="names"  >
    <label >mario</label>
    <input value="mario" type="checkbox" v-model="names"  >
    <label >skill</label>
    <input type="text" v-model="tempSkill" @keyup.alt="addSkill">
  </form>
  <p>{{password}},{{email}}</p>
  <p>{{role}},{{terms}}</p>
  <p>{{names}}</p>
  <div v-for="skill in skills" :key="skill">
  {{skill}}
  </div>
</template>

<script>
export default {
  data(){
    return {
      email:'',
      password:'',
      role:'',
      terms: false,
      names:[],
      tempSkill:'',  
      skills:[]
    }
  },
  methods:{
    addSkill(e){
      if(e.key === ',' && this.tempSkill){
        if(!this.skills.includes(this.tempSkill)){
          this.skills.push(this.tempSkill)
        }
          this.tempSkill =''
      }
    }
  }
}
</script>

<style>
  
</style>

