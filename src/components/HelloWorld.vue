<template>
  <center>
  <div class="container">
       <h3 class="p-3 text-center">DAY 11 TASK 2</h3>
       <table class="table table-striped table-bordered">
           <thead>
               <tr>
                   <th>ID</th>
                   <th>Email</th>
                   <th>First Name</th>
                   <th>Last Name</th>
                   <th>Avatar</th>
               </tr>
           </thead>
           <tbody>
               <tr class="item" v-for="item in list" :key="item.id">
                   <td>{{item.id}}</td>
                   <td>{{item.email}}</td>
                   <td>{{item.first_name}}</td>
                   <td>{{item.last_name }}</td>
                   <td><img :src="item.avatar"/></td>
               </tr>
           </tbody>
       </table>
   </div>    
   </center>
</template>

<script>
import axios from "axios";
export default {
 name: 'App',
 data(){
   return {
     list:[]
   }
 },
 async mounted(){
     let result = await axios.get("https://reqres.in/api/users?page=2");
     console.warn(result.data.data);
     this.list =result.data.data;
 }

};
</script>

<style>
table,tr,td{
 border: 2px solid black;
 border-collapse: collapse;
}

</style>