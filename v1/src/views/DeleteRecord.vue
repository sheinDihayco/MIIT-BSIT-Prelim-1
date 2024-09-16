<template>
  <div class="wrapper">
    <Sidebar />
    <div class="main-panel">
      <div class="p-5">
        <h1>Instruction:</h1>
        <p>
          <span>Update Age using the below link:</span><br />
          <span
            >https://api.jlipreso.com/miit/public/api/user/deleteByID/{id}</span
          >
        </p>
        <div class="card">
          <div class="card-body">
            <table class="table">
              <tbody>
                <tr>
                  <td>Enter ID No.:</td>
                  <td>
                    <input class="form-control" type="number" v-model="id" />
                  </td>
                  <td>
                    <button class="btn btn-danger" @click="deleteUser(id)">
                      Delete
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
  name: 'DeleteRecord',
  components: { Sidebar },
  data() {
    return {
      users: {} as any,
      id: 0,
    };
  },
  methods: {
    async deleteUser(id: number) {
      const response = await axios.get(
        `https://api.jlipreso.com/miit/public/api/user/deleteByID/${id}`
      );
      Swal.fire({
        title: 'Successful',
        text: 'Deleted Successfully',
        icon: 'success',
      }).then(async () => {
        this.id = 0;
      });
      this.users = response.data;
    },
  },
};
</script>
