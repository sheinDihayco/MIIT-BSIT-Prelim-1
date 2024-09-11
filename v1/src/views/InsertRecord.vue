<template>
  <div class="wrapper">
    <Sidebar/>
    <div class="main-panel">
      <div class="p-5 w-50">
        <h1>Instruction:</h1>
        <p>
          <span>Use the below API link to insert record</span><br/>
          <span>https://api.jlipreso.com/miit/public/api/user/insertRecord/{fname}/{lname}/{age}</span>
        </p>
        <div class="card">
          <div class="card-body">
            <table class="table">
              <tbody>
                <tr>
                  <td>First name</td>
                  <td><input class="form-control" type="text"></td>
                </tr>
                <tr>
                  <td>Last name</td>
                  <td><input class="form-control" type="text"></td>
                </tr>
                <tr>
                  <td>Age</td>
                  <td><input class="form-control" type="number"></td>
                </tr>
                <tr>
                  <td></td>
                  <td><button class="btn btn-primary w-100">Submit</button></td>
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
