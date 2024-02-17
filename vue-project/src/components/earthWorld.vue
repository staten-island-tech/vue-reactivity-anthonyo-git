<template>
  <div class="game-container">
    <div class="money-display">${{ money }}</div>
    <div class="rectangle" v-for="(business, index) in businesses" :key="index" @click="addMoney(business.profit)">
      {{ business.name }}  {{ business.profit }}$
      <img :src="business.image" class="imageBusinesses"/>
    </div>
  </div>
</template>
  <!-- <button @click="count++">Add 1</button>
  <p>Count is: {{ count }}</p>
    <div class="circle" v-for="(circle, index) in circles" :key="index">
      {{ circle.name }}
    </div> -->

<script setup>
import { ref } from 'vue';

const money = ref(0);

const addMoney = (amount) => {
  money.value += amount;
};


// setInterval(() => {
//   money.value +=  1; 
// },  1000)

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



const businesses = ref([
  {
    id: 'lemonadeStand',
    rectangleNum:  1,
    name: 'Lemonade stand',
    price:  1,
    timeTaken:  1,
    quantityPurchased:  1,
    profit:  1,
    image: '/assets/lemon.png',
  },
  {
    id: 'newspaperDelivery',
    rectangleNum:  2,
    name: 'Newspaper Deliver',
    price:  30,
    timeTaken:  3,
    quantityPurchased:  0,
    profit:  25,
    image: '/assets/newspaper.png',
  },
  {
    id: 'carWash',
    rectangleNum:  3,
    name: 'Car Wash',
    price:  500,
    timeTaken:  6,
    quantityPurchased:  0,
    profit:  300,
    image: '/assets/car.png',
  },
  {
    id: 'pizzaDelivery',
    rectangleNum:  4,
    name: 'Pizza Delivery',
    price:  3000,
    timeTaken:  12,
    quantityPurchased:  0,
    profit:  2000,
    image: '/assets/pizza.png',
  },
  {
    id: 'donutShop',
    rectangleNum:  5,
    name: 'Donut Shop',
    price:  50000,
    timeTaken:  30,
    quantityPurchased:  0,
    profit:  20000,
    image: '/assets/donut.png',
  },
  {
    id: 'shrimpBoat',
    rectangleNum:  6,
    name: 'Shrimp Boat',
    price:  800000,
    timeTaken:  90,
    quantityPurchased:  0,
    profit:  4000000,
    image: '/assets/boat.png',
  },
  {
    id: 'hockeyTeam',
    rectangleNum:  7,
    name: 'Hockey Team',
    price:  6000000,
    timeTaken:  600,
    quantityPurchased:  0,
    profit:  4000000,
    image: '/assets/hockey.png',
  },
  {
    id: 'movieStudio',
    rectangleNum:  8,
    name: 'Movie Studio',
    price:  100000000,
    timeTaken:  3600,
    quantityPurchased:  0,
    profit:  40000000,
    image: '/assets/movie.png',
  },
  {
    id: 'bank',
    rectangleNum:  9,
    name: 'Bank',
    price:  5000000000,
    timeTaken:  36000,
    quantityPurchased:  0,
    profit:  1000000000,
    image: '/assets/bank.png',
  },
  {
    id: 'oilCompany',
    order:  10,
    name: 'Oil Company',
    price:  153434564431,
    timeTaken:  36000,
    quantityPurchased:  0,
    profit:  51434564431,
    image: '/assets/company.png',
  },
]);

</script>

<style scoped>

.imageBusinesses {
  height: 1000%;
  width: 1000%
}
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
  cursor: pointer
}

</style>

// notes
// https://vuejs.org/guide/essentials/list
// https://adventure-capitalist.fandom.com/wiki/Businesses
// css cover x until money balance is reaches a certain amount