<template>
  <div id="app">
    <custom-table :members="employees"/>
  </div>
</template>

<script>
import CustomTable from './components/CustomTable.vue'
export default {
  name: 'App',
  components: { CustomTable },
  data() {
    return {
      employees: [
        {
          imgURL: '',
          name: 'Sarah Connor',
          team: 'Crosty',
          role: 'Team Lead',
          gmail: 'sarahconnor@gmail.com',
          birthday: '25.04.1994',
          telegram: '@sarahconnor',
          lastLogin: '03.11.2021',
          sex: 'woman',
          online: true
        },
        {
          imgURL: '',
          name: 'John Doe',
          team: 'Alpha',
          role: 'Developer',
          gmail: 'johndoe@gmail.com',
          birthday: '12.09.1988',
          telegram: '@johndoe',
          lastLogin: '15.10.2021',
          sex: 'man',
          online: true
        },
        {
          imgURL: '',
          name: 'Alice Smith',
          team: 'Beta',
          role: 'Designer',
          gmail: 'alicesmith@gmail.com',
          birthday: '18.07.1990',
          telegram: '@alicesmith',
          lastLogin: '29.08.2021',
          sex: 'woman',
          online: false
        }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: "Commissioner", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
