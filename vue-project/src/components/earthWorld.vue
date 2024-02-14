
<script setup>
import { ref } from 'vue';

const money = ref(0);

setInterval(() => {
  money.value +=  1231; 
},  1231)

const rectangles = ref([
  { name: 'Lemonade Stand Outline' },
  { name: 'Newspaper Delivery Outline' },
  { name: 'Car Wash Outline' },
  { name: 'Pizza Delivery Outline' },
  { name: 'Donut Shop Outline' },
  { name: 'Shrimp Boat Outline' },
  { name: 'Hockey Team Outline' },
  { name: 'Movie Studio Outline' },
  { name: 'Bank Outline' },
  { name: 'Oil Company Outline' },
]);



// const businesses = ref([
//  {
//     id: 'lemonadeStand',
//     rectangleNum: 1,
//     name: 'Lemonade stand',
//     price: 1,
//     timeTaken: 1,
//     quantityPurchased: 1,
//     profit: 1,
//     image: 'lemon.png',
//   },
//   {
//     id: 'newspaperDelivery',
//     rectangleNum: 2,
//     name: 'Newspaper Deliver',
//     price: 30,
//     timeTaken: 3,
//     quantityPurchased: 0,
//     profit: 25,
//     image: 'newspaper.png',
//   },
//   {
//     id: 'carWash',
//     rectangleNum: 3,
//     name: 'Car Wash',
//     price: 500,
//     timeTaken: 6,
//     quantityPurchased: 0,
//     profit: 300,
//     image: 'car.png',
//   },
//   pizzaDelivery, {
//     id: 'pizzaDelivery',
//     rectangleNum: 4,
//     name: 'Pizza Delivery',
//     price: 3000,
//     timeTaken: 12,
//     quantityPurchased: 0,
//     profit: 2000,
//     image: 'pizza.png',
//   },
//   {
//     id: 'donutShop',
//     rectangleNum: 5,
//     name: 'Donut Shop',
//     price: 50000,
//     timeTaken: 30,
//     quantityPurchased: 0,
//     profit: 20000,
//     image: 'donut.png',
//   },
//   {
//     id: 'shrimpBoat',
//     rectangleNum: 6,
//     name: 'Shrimp Boat',
//     price: 800000,
//     timeTaken: 90,
//     quantityPurchased: 0,
//     profit: 400000,
//     image: 'boat.png',
//   },
//   {
//     id: 'hockeyTeam',
//     rectangleNum: 7,
//     name: 'Hockey Team',
//     price: 6000000,
//     timeTaken: 600,
//     quantityPurchased: 0,
//     profit: 4000000,
//     image: 'hockey.png',
//   },
//   {
//     id: 'movieStudio',
//     rectangleNum: 8,
//     name: 'Movie Studio',
//     price: 100000000,
//     timeTaken: 3600,
//     quantityPurchased: 0,
//     profit: 40000000,
//     image: 'movie.png',
//   },
//   {
//     id: 'bank',
//     rectangleNum: 9,
//     name: 'Bank',
//     price: 5000000000,
//     timeTaken: 36000,
//     quantityPurchased: 0,
//     profit: 1000000000,
//     image: 'bank.png',
//   },
//   {
//     id: 'oilCompany',
//     order: 10,
//     name: 'Oil Company',
//     price: 153434564431,
//     timeTaken: 36000,
//     quantityPurchased: 0,
//     profit: 51434564431,
//     image: 'company.png',
//   },
// ]);

</script>



<template>
  <div div class="game-container">
    <div class="rectangle" v-for="(rectangle, index) in rectangles" :key="index" > {{ rectangle.name }} </div>
  </div>
    <!-- <div class="circle" v-for="(circle, index) in circles" :key="index">
      {{ circle.name }}
    </div> -->

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