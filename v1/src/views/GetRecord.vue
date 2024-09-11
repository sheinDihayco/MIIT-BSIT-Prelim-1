<template>
  <div class="wrapper">
    <Sidebar/>
    <div class="main-panel">
      <div class="p-5 w-75">
        <h1>Instruction:</h1>
        <p>
          <span>Get Records using the below API link:</span><br/>
          <span>https://api.jlipreso.com/miit/public/api/user/getAll</span>
        </p>
        <div class="card">
          <div class="card-body">
            <button class="btn btn-primary">Get All Users</button>
            <table class="table table-striped mt-5">
              <thead>
                <tr>
                  <th class="bg-dark text-white">Number</th>
                  <th class="bg-dark text-white">First name</th>
                  <th class="bg-dark text-white">Last name</th>
                  <th class="bg-dark text-white">Age</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(user, i) in 3" :key="i">
                  <td>{{ (i + 1) }}</td>
                  <td></td>
                  <td></td>
                  <td></td>

                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">

  import Sidebar from "@/components/Sidebar.vue";

  export default {
    components: { Sidebar }
  }

</script>
