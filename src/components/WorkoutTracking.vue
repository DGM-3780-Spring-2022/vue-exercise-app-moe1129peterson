<template>
  <div class="container">
    <h2 class="text-center mt-5">workout-tracking</h2>
    
   <!--  Input -->
   <div class="d-flex ">
     <input v-model="workout" type="text" placeholder="Enter Exercise" class="form-control">
     <input v-model="time" type="number" placeholder="Enter Time" class="form-control">
     <input v-model="distance" type="number" placeholder="Enter Distance" class="form-control">
     <input v-model="date" type="date" placeholder="" class="form-control">

     <button @click="submitWorkout" class="btn btn-success rounded-0">Submit</button>
   </div>

  <!-- Table -->
<table class="table table-bordered mt-5">
  <thead>
    <tr>
      <th scope="col">Workout Name</th>
      <th scope="col">Time</th>
      <th scope="col">Distance</th>
      <th scope="col">Date</th>
    </tr>
  </thead>
  
  <tbody>
    <tr v-for="(workout, index) in workouts" :key="index">
      <td>{{workout.workout}}</td>
      <td>{{workout.time}} min</td>
      <td>{{workout.distance}} km</td>
      <td>{{workout.date}}</td>
      <!--
      <td>
        <div class="text-center" @click="deleteWorkout(index)">
          <span class="fa fa-trash"></span>
        </div>
      </td>
      !-->
    </tr>
  </tbody>
</table>

  <!-- Stats Table-->
<table class="table table-bordered mt-5">
  <thead>
    <tr>
      <th scope="col">Total Workouts</th>
      <th scope="col">Total Time</th>
      <th scope="col">Total Distance</th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>{{totalWorkouts}}</td>
      <td>{{totalTimes}}</td>
      <td>{{totalDistances}}</td>
      <!--
      <td>
        <div class="text-center" @click="deleteWorkout(index)">
          <span class="fa fa-trash"></span>
        </div>
      </td>
      !-->
    </tr>
  </tbody>
</table>


   
  </div>
</template>

<script>
export default {
    name: 'workout-tracking', 
    props: {
      msg: String,
    },

    data(){
      return{
        workout:'',
        workouts: [
         
        ],
        totalWorkouts: 0,
        totalTimes: 0,
        totalDistances: 0,
        totalTime: 0,
      }
    },

    methods: {
      submitWorkout(){
        if(this.workout.length === 0) return

        this.workouts.push({
          workout: this.workout,
          time: this.time,
          distance:this.distance,
          date: this.date,
        });

        this.totals();

      },

      totals() {
      this.totalWorkouts = 0;
      this.totalTimes = 0;
      this.totalDistances = 0;
    
      for (let i = 0; i < this.workouts.length; i++) {
        this.totalWorkouts += 1;
        this.totalTimes += parseInt(this.workouts[i].time);
        this.totalDistances += parseInt(this.workouts[i].distance);
      }
      
    }

    


      

    }, 


    


}


</script>

<style scoped>

table th{
  padding : 10px;
}

table td{
  padding : 10px;
}




</style>