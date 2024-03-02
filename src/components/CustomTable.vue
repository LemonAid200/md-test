<template>
  <div class="table-wrapper">


    <div class="team-stats">
     <div class="team-stats_intro">
      <div class="team-stats_intro_icon">
        <img src="../../public/team.svg" alt="">
      </div>
      <h2>Team</h2>
      <div class="team-stats_info">
        <img src="" alt="">
      </div>
     </div>

     <div class="team-stats_item" v-for="item in teamInfoStats" :key="item.name">
      <h1>{{ item.value }}</h1>
      <p>{{ item.name }}</p>
     </div>
    </div>


    <button class="addEmployee">Add new employee</button>
    <table>
      <thead></thead>
      <tbody></tbody>
    </table>
  </div>
</template>
<script>
export default {
  name: 'CustomTable',
  props: {
    members: {
      type: Array,
      required: true
    }
  },
  components: {},
  computed: {
    teamInfoStats(){
      
      return [
        {
          value: this.members.length, 
          name: 'members'
        }, 
        {
          value: this.members.reduce((acc, cur) => {if(cur.online) acc++; return acc}, 0),
          name: 'online'
        },
        {
          value: this.members.reduce((acc, cur) => {if(cur.sex === 'man') acc++; return acc}, 0),
          name: 'men'
        },
        {
          value: this.members.reduce((acc, cur) => {if(cur.sex === 'woman') acc++; return acc}, 0),
          name: 'women'
        }
      ]
    }
  }
}
</script>
<style scooped>
*{
  margin: 0;padding: 0;
}
h1{
  font-size: 22px;
  font-weight: 500;
  line-height: 130%;
  letter-spacing: 0%;
}
h2{
  color: rgb(42, 53, 90);
  font-family: Commissioner;
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
  letter-spacing: 0px;
  text-align: left;
}
.table-wrapper {
  background: rgb(245, 247, 251);
  padding: 28px;
}
.team-stats {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: flex-start;
  padding: 16px 28px;
  border-radius: 12px;
  background: rgb(255, 255, 255);
}
.team-stats_intro{
  display: flex;
  align-self: center;
  align-items: center;
  gap: 16px;
}
.team-stats_intro_icon{
  width: 32px;
  height: 32px;
  border-radius: 8px;
  display: flex;
  background: rgb(243, 249, 255);
  align-items: center;
  justify-content: center;
}
.team-stats_item{
  text-align: left;
  padding: 0 36px;
  border-right: 1px solid rgb(229, 232, 239);;
}

.team-stats_item p{
  color: rgb(133, 145, 174);
  font-size: 12px;
  font-weight: 400;
  line-height: 150%;
}
</style>
