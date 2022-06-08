<template>
  <div class="container">
    <img class="img1" src="../assets/img1.png" alt="" />
    <table class="container">
      <tr class="wraper">
        <th class="column-table">Name</th>
        <th class="column-table">Gander</th>
        <th class="column-table">religion</th>
        <th class="column-table">Phone</th>
        <th class="column-table">Address</th>
        <th class="column-table">NIK</th>
        <th class="column-table">Actions</th>
      </tr>
      <tr class="wraper" v-for="(allpasien,index) in allpasiens" v-bind:key="index" >
        <td class="value-table">{{allpasien.fullName}}</td>
        <td class="value-table">{{allpasien.gender}}</td>
        <td class="value-table">{{allpasien.religion}}</td>
        <td class="value-table">{{allpasien.phone}}</td>
        <td class="value-table">{{allpasien.adress}}</td>
        <td class="value-table">{{allpasien.nik}}</td>
        <td class="value-table-action">
          <button v-on:click="handlebutton2" class="button1">update</button>
          <button v-on:click="handledelete" class="button2">delete</button>
        </td>
      </tr>
    </table>
    <div class="wraperButton">
    <button v-on:click="handlebutton" class="button1">create</button>
    </div>
    <div v-if="isActive === true"  class="modal">
        <div class="modal-content">
          <p>Create Pasien</p>
          <div class="wraperinput">
          <input class="inputtext" type="text" placeholder="name">
          <input class="inputtext" type="text" placeholder="Gander">
          <input class="inputtext" type="text" placeholder="religion">
          <input class="inputtext" type="text" placeholder="Phone">
          <input class="inputtext" type="text" placeholder="Adress">
          <input class="inputtext" type="text" placeholder="NIK">
          </div>
          <button id="myBtn" v-on:click="handlebutton" class="button-modal">Create</button>
        </div>
    </div>
    <div v-if="isActive2 === true"  class="modal">
        <div class="modal-content">
          <p>Update Pasien</p>
          <div class="wraperinput">
          <input class="inputtext" type="text" placeholder="name">
          <input class="inputtext" type="text" placeholder="Gander">
          <input class="inputtext" type="text" placeholder="religion">
          <input class="inputtext" type="text" placeholder="Phone">
          <input class="inputtext" type="text" placeholder="Adress">
          <input class="inputtext" type="text" placeholder="NIK">
          </div>
          <button id="myBtn" v-on:click="handlebutton2" class="button-modal">Update</button>
        </div>
    </div>
        <div v-if="isActive3 === true"  class="modal">
        <div class="modal-content">
          <p>Apakah anda yakin ingin menghapus data pasien ?</p>
          <div class="wraperdelete">
          <button id="myBtn" v-on:click="handledelete" class="button-modal">Yess</button>
          <button id="myBtn" v-on:click="handledelete" class="button-modal1">No</button>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  data: function () {
    return {
      isActive: false,
      isActive2: false,
      isActive3: false,
      pasien: {
        fullName: '',
        gender: '',
        sex: '',
        phone: '',
        adress: '',
        religion: '',
        nik: ''
      },
      allpasiens: [
        {
          id: 1,
          fullName: 'joko sutrisno',
          gender: 'male',
          phone: '823462364',
          adress: 'jalan kenangan 2',
          religion: 'islam',
          nik: '342342893642'
        },
        {
          id: 2,
          fullName: 'dewi indah',
          gender: 'female',
          phone: '324234',
          adress: 'jalan mawar 7',
          religion: 'islam',
          nik: '87634683'
        },
        {
          id: 3,
          fullName: 'pita diah saputri',
          gender: 'female',
          phone: '56834659',
          adress: 'jalan kimaja blok a7',
          religion: 'islam',
          nik: '563846387434'
        },
        {
          id: 4,
          fullName: 'depriansyah',
          gender: 'male',
          phone: '3965986589',
          adress: 'jalan ratu dibalau blok c4',
          religion: 'islam',
          nik: '8764587459'
        }
      ]
    }
  },
  methods: {
    handlebutton () {
      this.isActive = !this.isActive
      console.log(this.isActive)
    },
    handlebutton2 () {
      this.isActive2 = !this.isActive2
      console.log(this.isActive2)
    },
    handledelete () {
      this.isActive3 = !this.isActive3
      console.log(this.isActive2)
    }
  },
  created () {
    document.title = 'Home'
  }
  // components: {
  //   HelloWorld
  // }
}
</script>

<style scoped src="../assets/style/home.css"></style>
