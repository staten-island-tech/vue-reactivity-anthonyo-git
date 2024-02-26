<template>
  <div class="body">    
    <div class="Heading-Bar">
      <div class="Captalist">
        <img src="https://i.imgur.com/fFc9Jsg.png" alt="captalistMan">
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

const businesses = ref([
  {
    name: 'Lemonade stand',
    price:  1,
    quantityPurchased:  1,
    profit:  1,
    image: 'https://i.imgur.com/uf6dPpY.png',
  },
  {
    name: 'Shrimp Boat',
    price:  800000,
    quantityPurchased:  0,
    profit: 622080,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/boat.png',
  },
  {
    name: 'Newspaper Deliver',
    price:  30,
    quantityPurchased:  0,
    profit:  60,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/newspaper.png',
  },
  {
    name: 'Hockey Team',
    price:  6000000,
    quantityPurchased:  0,
    profit:  7464960,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/hockey.png',
  },
  {
    name: 'Car Wash',
    price:  500,
    quantityPurchased:  0,
    profit:  540,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/car.png',
  }, 
  {
    name: 'Movie Studio',
    price:  100000000,
    quantityPurchased:  0,
    profit:  89579520,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/movie.png',
  },
  {
    name: 'Pizza Delivery',
    price:  3000,
    quantityPurchased:  0,
    profit:  4320,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/pizza.png',
  }, 
  {
    name: 'Bank',
    price:  5000000000,
    quantityPurchased:  0,
    profit:  1074954520,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/bank.png',
  },
  {
    name: 'Donut Shop',
    price:  50000,
    quantityPurchased:  0,
    profit:  51840,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/donut.png',
  },
  {
    name: 'Oil Company',
    price:  153434564431,
    quantityPurchased:  0,
    profit:  29668737024,
    image: 'https://10288944-884245489883600444.preview.editmysite.com/uploads/b/4181373-341607469518366532/files/images/company.png',
  },
]);

</script>

<style scoped>

.body {
  font-family: "Comic Sans",cursive;
  font-size: 18px;
  color: #dedede;
  font-weight: 700;
  background-color: #141414;
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.imageBusinesses {
  height: 64px;
  width: 64px;
}

.Heading-Bar {
  background-color: #473f3fb6;   
  display: flex;
  align-items: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.Captalist img {
  width: 13vw;
}

.money-display {
  font-size: 44px;
  font-weight: bold;
  color:white;
}

.game-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center; 
  align-items: center; 
  padding: 20px;
  flex-grow: 1;
}

.business-item {
  display: flex;
  align-items: center;
  margin: 10px;
}

.rectangle {
  width: 35vw;
  height: 11vh;
  background-color: #425270;
  border-radius: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 10px; 
}

</style>

// notes
// https://vuejs.org/guide/essentials/list
// https://adventure-capitalist.fandom.com/wiki/Businesses
// css cover x until money balance is reaches a certain amount
// https://gaming.stackexchange.com/questions/330133/what-s-the-price-scaling-for-businesses