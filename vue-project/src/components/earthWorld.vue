<template>
  <button @click="count++">Add 1</button>
  <p>Count is: {{ count }}</p>
  <div div class="game-container">
    <div class="rectangle" v-for="(rectangle, index) in rectangles" :key="index" > {{ rectangle.name }} </div>
    <div class="money-display">${{ money }}</div>
  </div>
    <!-- <div class="circle" v-for="(circle, index) in circles" :key="index">
      {{ circle.name }}
    </div> -->

</template>


<script setup>
import { ref } from 'vue';

const money = ref(0);

setInterval(() => {
  money.value +=  1; 
},  1000)

const rectangles = ref([
  { name: 'Lemonade Stand  ' },
  { name: 'Newspaper Delivery  ' },
  { name: 'Car Wash  ' },
  { name: 'Pizza Delivery  ' },
  { name: 'Donut Shop  ' },
  { name: 'Shrimp Boat  ' },
  { name: 'Hockey Team  ' },
  { name: 'Movie Studio  ' },
  { name: 'Bank  ' },
  { name: 'Oil Company  ' },
]);

</script>

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
  flex-basis: calc(50% - 100px);
  width:  1200px; 
  height:  125px; 
  background-color: #eee; 
  border:  1px solid #000;
  margin:  10px;
}

</style>

// notes
// https://vuejs.org/guide/essentials/list
// https://adventure-capitalist.fandom.com/wiki/Businesses