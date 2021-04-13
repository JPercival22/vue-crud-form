<template>
  <div class="skills">
    <div class="holder">

      <form @submit.prevent="addSkill">
        <input type="text" placeholder="Enter a Skill that you have..." v-model="skill"> 
        {{ skill }}
        <!-- v-model is implicated here to capture the users input-->
      </form>
      <ul>
        <li v-for="(data, index) in skills" :key='index'>{{index}}. {{data.skills}}</li>
        <!-- loops through the data and the index in skills array then interpolates the index and data into the skills table-->
      </ul>
      <p>These are the skills that you possess</p>

    </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      skill: '',
      skills: [
        {"skills": "UX Researcher/ Designer"},
        {"skills": "UI designer"},
        {"skills": "Front End Developer"},
        {"skills": "Vue.js"}
      ]
    }
  },
  methods: {
    addSkill() {
      this.skills.push({skills: this.skill})
      this.skill = '';
    }
  }
}
</script>

<style scoped>

  .holder {
    background: #fff;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }

  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }

  .container {
    box-shadow: 0px 0px 40px lightgray;
  }
  input {
    width: calc(100% - 40px);
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background: #323333;
    color: #FFFFFF;
  }

</style>
