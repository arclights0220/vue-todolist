<template>
  <div class="home">
    <!-- <div v-if="hello">
      a
    </div>
    <div v-else>
      b
    </div>-->
    <!-- input받는거 실시간으로 -->
    <!-- <input type="text" v-model="input">
    {{input}}-->
    <!-- key는 같으면 안됨
    <div v-for="item in arr" :key="item">
      {{item}}
    </div>-->
    <!-- 실시간으로 변하는 것
    <div v-if="toggle">HEllo</div>
    <div v-else>World</div>
    <button @click="toggleFunction">Click</button>--> 
   
    <div>
      <input type="text" v-model="curName" />
      <br />
      <input type="number" v-model="curCom" />
      <button @click="addClub">추가하기</button>
    </div>
     <ClubList :clublist="data" />
  </div>
</template>
 
<script>
import ClubList from "../components/ClubList.vue";
export default {
  //data라는 함수에 return값으로 변수 선언
  components: {
    ClubList
  },
  methods: {
    addClub(){
      this.data.push({
        name : this.curName,
        computer: this.curCom
      })
    }
  },
  data() {
    return {
      curName: "",
      curCom: 0,
      // hello:1,

      // arr:["I","W","O","P"],

      // toggle: false
      data: [
        {
          name: "EDCAN",
          computer: 16,
          check:false
        },
        {
          name: "IWOP",
          computer: 9,
          check:false
        }
      ]
    };
  }
  // methods: {
  //   toggleFunction() {
  //     this.toggle = !this.toggle;
  //   }
  // }
};
</script>

<style>
.home {
  
}
</style>