<template>
<div>
     <div class="club" :class="{'club-check':club.check}" v-for="(club,idx) in clublist" :key="club.name">
      <h1> {{club.name}} </h1>
      <p>컴퓨터실 : {{club.computer}} </p>
      <button @click="deleteThis(idx)">삭제</button>
      <button @click="checkThis(idx)">확인</button>
    </div>
</div>
</template>

<script>
export default {
    props:{
        clublist: Array
    },
    methods:{
        deleteThis(index){
            this.clublist.splice(index,1);
        },
        checkThis(index){
            this.clublist[index].check = true;
        }
    }
}
</script>

<style scoped>
.club{
    background-color: beige;
}
.club-check{
    color: #aaefde;
}
</style>

