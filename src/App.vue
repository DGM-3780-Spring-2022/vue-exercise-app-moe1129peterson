<template>
  <WorkoutTracking />
</template>

<script>
import WorkoutTracking from './components/WorkoutTracking.vue'

export default {
  name: 'App',
  components: {
    WorkoutTracking
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
  margin-top: 60px;
}
</style>
