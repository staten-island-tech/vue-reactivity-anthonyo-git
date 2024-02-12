<script setup>
import { ref } from 'vue';

const money = ref(0);

setInterval(() => {
  money.value +=  1231; 
},  1)
</script>



<template>
  <div class="game-container">
    <div class="money-display">${{ money }}</div>
    <div class="rectangle" v-for="x in  10" :key="x">
    </div>
    <div v-for="(key, index) in arrayName">

    </div>
  </div>
</template>

<style scoped>

.money-display {
  position: absolute;
  top: 10px; 
  left: 10px; 
  font-size: 35px;
}

.game-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
}


.rectangle {
  flex-basis: calc(50% - 100px);;
  width:  1200px; 
  height:  125px; 
  background-color: #eee; 
  border:  1px solid #000;
  margin:  10px;
}

</style>
