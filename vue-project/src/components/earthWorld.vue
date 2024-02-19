<template>
  <div class="body">    
    <div class="Heading-Bar">
      <div class="Captalist">
        <img src="https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/capitalist.png" alt="captalistMan">
      </div>
      <div class="money-display">${{ money }}</div>
    </div>
    <div class="game-container">
      <div v-for="(business, index) in businesses" :key="index" class="business-item">
        <img :src="business.image" class="imageBusinesses"/>
        <div class="rectangle" @click="addMoney(business.profit)">
          {{ business.name }}   
          ${{ business.profit }}
        </div>
      </div>
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
    image: 'https://i.imgur.com/uf6dPpY.png',
  },
  {
    id: 'newspaperDelivery',
    rectangleNum:  2,
    name: 'Newspaper Deliver',
    price:  30,
    timeTaken:  3,
    quantityPurchased:  0,
    profit:  25,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/newspaper.png',
  },
  {
    id: 'carWash',
    rectangleNum:  3,
    name: 'Car Wash',
    price:  500,
    timeTaken:  6,
    quantityPurchased:  0,
    profit:  300,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/car.png',
  },
  {
    id: 'pizzaDelivery',
    rectangleNum:  4,
    name: 'Pizza Delivery',
    price:  3000,
    timeTaken:  12,
    quantityPurchased:  0,
    profit:  2000,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/pizza.png',
  },
  {
    id: 'donutShop',
    rectangleNum:  5,
    name: 'Donut Shop',
    price:  50000,
    timeTaken:  30,
    quantityPurchased:  0,
    profit:  20000,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/donut.png',
  },
  {
    id: 'shrimpBoat',
    rectangleNum:  6,
    name: 'Shrimp Boat',
    price:  800000,
    timeTaken:  90,
    quantityPurchased:  0,
    profit:  4000000,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/boat.png',
  },
  {
    id: 'hockeyTeam',
    rectangleNum:  7,
    name: 'Hockey Team',
    price:  6000000,
    timeTaken:  600,
    quantityPurchased:  0,
    profit:  4000000,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/hockey.png',
  },
  {
    id: 'movieStudio',
    rectangleNum:  8,
    name: 'Movie Studio',
    price:  100000000,
    timeTaken:  3600,
    quantityPurchased:  0,
    profit:  40000000,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/movie.png',
  },
  {
    id: 'bank',
    rectangleNum:  9,
    name: 'Bank',
    price:  5000000000,
    timeTaken:  36000,
    quantityPurchased:  0,
    profit:  1000000000,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/bank.png',
  },
  {
    id: 'oilCompany',
    order:  10,
    name: 'Oil Company',
    price:  153434564431,
    timeTaken:  36000,
    quantityPurchased:  0,
    profit:  51434564431,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/company.png',
  },
]);

</script>

<style scoped>

.body {
  font-family: "Comic Sans",cursive;
  font-weight: bold;
  font-size:   18px;
  color: #dedede;
  font-weight:   700;
  background-color: #242121a8;
}

.imageBusinesses {
  height:   64px;
  width:   64px;
}

.Heading-Bar {
  background-color: #473f3fb6;   
  padding:   20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.Captalist img {
  width:   10%;
}

.money-display {
  font-size:   24px;
  font-weight: bold;
  color:white;
}

.game-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center; 
  align-items: center; 
}

.business-item {
  display: flex;
  align-items: center;
  margin:   10px;
}

.rectangle {
  width:   1200px;
  height:   125px;
  border:   1px solid #50474700;
  cursor: pointer;
  background-color: #8c8176;
  border-radius:   10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-left:   10px; 
}

</style>

// notes
// https://vuejs.org/guide/essentials/list
// https://adventure-capitalist.fandom.com/wiki/Businesses
// css cover x until money balance is reaches a certain amount