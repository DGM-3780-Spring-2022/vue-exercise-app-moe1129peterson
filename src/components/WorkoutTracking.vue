<template>
  <div id= "workingout-table">
      <h1>Workout List</h1>
      <table align= "center" border="1" >
        <thead>
          <tr>
            <th>Exercise</th>
            <th>Time</th>
            <th>Distance</th>  
          </tr>
        </thead>
        <tbody>
          <tr>
             <td>Run</td>
             <td>5min</td>
             <td>200m</td>
          </tr>
          <tr>
             <td>Swim</td>
             <td>10min</td>
             <td>200m</td>
          </tr>
          <tr>
             <td>Bike</td>
             <td>5min</td>
             <td>500m</td>
          </tr>
        </tbody>
      </table>
  </div>
</template>

<script>
export default {
    name: 'workout-tracking'

}
</script>

<style scoped>

table th{
  padding : 20px;
}


</style>