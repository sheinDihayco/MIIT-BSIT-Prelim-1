<template>
  <div class="wrapper">
    <Sidebar />
    <div class="main-panel">
      <div class="p-5 w-75">
        <h1>Instruction:</h1>
        <p>
          <span>Update Age using the below link:</span><br />
          <span
            >https://api.jlipreso.com/miit/public/api/user/updateRecord/{id}/{age}</span
          >
        </p>
        <div class="card">
          <div class="card-body">
            <table class="table">
              <tbody>
                <tr>
                  <td style="width: 50px">ID</td>
                  <td>
                    <input class="form-control" type="text" v-model="id" />
                  </td>
                  <td style="width: 50px">Age</td>
                  <td>
                    <input
                      class="form-control"
                      v-model="newAge"
                      type="number"
                    />
                  </td>
                  <td>
                    <button class="btn btn-primary" @click="editAge(id)">
                      Update Age
                    </button>
                  </td>
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
import axios from 'axios';
import Swal from 'sweetalert2';
import Sidebar from '@/components/Sidebar.vue';

export default {
  name: 'EditRecord',
  components: { Sidebar },
  data() {
    return {
      users: {} as any,
      id: 0,
      newAge: '',
    };
  },
  methods: {
    async editAge(id: number) {
      const response = await axios.get(
        `https://api.jlipreso.com/miit/public/api/user/updateRecord/${id}/${this.newAge}`
      );
      Swal.fire({
        title: 'Successful',
        text: 'Updated Successfully',
        icon: 'success',
      });
      this.users = response.data;
    },
  },
};
</script>
