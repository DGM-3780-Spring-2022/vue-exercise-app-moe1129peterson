<template>
  <div class="container">
    <h2 class="text-center mt-5">workout-tracking</h2>
    
   <!--  Input -->
   <div class="d-flex ">
     <input v-model="workout" type="text" placeholder="Enter Exercise" class="form-control">
     <input v-model="time" type="text" placeholder="Enter Time" class="form-control">
     <input v-model="distance" type="text" placeholder="Enter Distance" class="form-control">

     <button @click="submitWorkout" class="btn btn-warning rounded-0">Submit</button>
   </div>

  <!-- Table -->
     <table class="table table-bordered mt-5">
  <thead>
    <tr>
      <th scope="col">Workout Name</th>
      <th scope="col">Time</th>
      <th scope="col">Distance</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(workout, index) in workouts" :key="index">
      <tb>{{workout.workoutname}}</tb>
      <td>{{workout.time}}</td>
      <td>{{workout.distance}}</td>
      <td>
      </td>
      <td>
        <div class="text-center" @click="deleteWorkout(index)">
          <span class="fa fa-trash"></span>
        </div>
      </td>
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
          {
            workoutname: "Run", 
            time:"3min",
            distance:"1km",
          },
          {
            workoutname: "Swim", 
            time:"3min",
            distance:"100m",
          },
        ]
      }
    },

    methods: {
      submitWorkout(){
        if(this.workout.length === 0) return;

        this.workouts.push({
          workoutname: this.workout,
          time: this.time,
          distance:this.distance,
        })
      }, 

      deleteWorkout(index){
        this.workouts.splice(index, 1);
      }, 

  

    }

}


</script>

<style scoped>

table th{
  padding : 20px;
}

table td{
  padding : 20px;
}

</style>