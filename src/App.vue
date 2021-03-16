<template>
  <div :class='App'>
    <Navbar/>
    <div :class='AppContainer'>
      <Banner :projects='projects' />
      <About/>
      <Projects :projects='projects' />
      <OpenPositions :jobs='jobs' />
      <Team :teams='teams' />
    </div>
    <Footer/>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import axios from 'axios';

import Navbar from './components/H-Layout/Navbar.vue';
import Banner from './components/H-Layout/Banner.vue';
import About from './components/H-Layout/About.vue';
import Projects from './components/H-Layout/Projects.vue'; 
import OpenPositions from './components/H-Layout/Open_Positions.vue';
import Team from './components/H-Layout/Team.vue'; 
import Footer from './components/H-Layout/Footer.vue'; 


export default defineComponent({
  name: 'App',
  components: {
    Navbar,
    Banner,
    About,
    Projects,
    OpenPositions,
    Team,
    Footer,
  },
  data() {
    return {
      App: 'w-screen',
      AppContainer: 'xl:container xl:mx-auto p-5',
      projects: [], 
      jobs: [],
      teams: [],
      error: 'value not found',
    }
  },
  async mounted () {
    try {
      const getProjects = await axios.get('http://localhost:1337/projects')
      this.projects = getProjects.data

      const getJobs = await axios.get('http://localhost:1337/jobs')
      this.jobs = getJobs.data

      const getTeams = await axios.get('http://localhost:1337/teams')
      this.teams = getTeams.data

    } catch (error) {
      this.error = error;
    }
  }, 
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
