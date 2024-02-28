<template>
  <div class="body">    
    <div class="Heading-Bar">
      <div class="Captalist">
        <img src="https://i.imgur.com/fFc9Jsg.png" alt="captalistMan">
      </div>
      <div class="money-display">${{ money.toFixed(2) }}</div>
      <div class="tax">30% tax every 5 second</div>
    </div>
    <div class="game-container">
      <div v-for="(business, index) in businesses" :key="index" class="business-item">
        <img :src="business.image" class="imageBusinesses"/>
        <div class="rectangle" @click="addMoney(business.profit)" v-bind:class="[money >= business.unlockCost ? 'unlocked' : '', '']">
          {{ business.name }}   
          ${{ business.profit }}
        </div>
      </div>
    </div>
  </div>
</template>
<!-- <div :class="[isActive ? activeClass : '', errorClass]"></div> -->
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


setInterval(() => {
  money.value /= 1.5; 
},  5000)

const businesses = ref([
  {
    name: 'Lemonade stand',
    price:  1,
    quantityPurchased:  1,
    profit:  1,
    image: 'https://freepngimg.com/thumb/adventure_time/127188-lemongrab-adventure-time-free-transparent-image-hd.png',
    unlockCost: 0,
  },
  {
    name: 'Shrimp Boat',
    price:  800000,
    quantityPurchased:  0,
    profit: 622080,
    image: 'https://i.imgur.com/dlfNmiV.png',
    unlockCost: 518400,
  },
  {
    name: 'Newspaper Deliver',
    price:  30,
    quantityPurchased:  0,
    profit:  60,
    image: 'https://i.imgur.com/SJm8Umj.png',
    unlockCost: 10,
  },
  {
    name: 'Hockey Team',
    price:  6000000,
    quantityPurchased:  0,
    profit:  7464960,
    image: 'https://i.imgur.com/AZTZlcQ.png',
    unlockCost: 6220800,
  },
  {
    name: 'Car Wash',
    price:  500,
    quantityPurchased:  0,
    profit:  540,
    image: 'https://i.imgur.com/4IexThd.png',
    unlockCost: 600,
  }, 
  {
    name: 'Movie Studio',
    price:  100000000,
    quantityPurchased:  0,
    profit:  89579520,
    image: 'https://i.imgur.com/bAB76pw.png',
    unlockCost: 7464960,
  },
  {
    name: 'Pizza Delivery',
    price:  3000,
    quantityPurchased:  0,
    profit:  4320,
    image: 'https://i.imgur.com/yoPEYN8.png',
    unlockCost: 5400,
  }, 
  {
    name: 'Bank',
    price:  5000000000,
    quantityPurchased:  0,
    profit:  1074954520,
    image: 'https://creazilla-store.fra1.digitaloceanspaces.com/cliparts/77406/bank-clipart-xl.png',
    unlockCost: 895795200,
  },
  {
    name: 'Donut Shop',
    price:  50000,
    quantityPurchased:  0,
    profit:  51840,
    image: 'https://i.imgur.com/pLxkI46.png',
    unlockCost: 43200,
  },
  {
    name: 'Oil Company',
    price:  153434564431,
    quantityPurchased:  0,
    profit:  29668737024,
    image: 'https://i.imgur.com/9dPkzkC.png',
    unlockCost: 1074954520,
  },
]);

</script>

<style scoped>

.body {
  font-family: "Comic Sans",cursive;
  font-size: 18px;
  font-weight: 700;
  background-color: #2e2525;
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.imageBusinesses {
  height: 70px;
  width: 70px;
}

.Heading-Bar {
  background-color: #221c1cb6;   
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
  background-color: #000000;
  border-radius: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 10px; 
  opacity: 0.5;
  cursor: not-allowed;
  pointer-events: none;
  color: rgb(161, 152, 152);
}

.tax { 
  position: absolute;
  margin-left: 85vw;
  color: #dedede;
}

.unlocked {
  cursor: pointer;
  opacity: 1;
  pointer-events: all;
  background-color: #425270;
  color: #dedede;
}



</style>

// notes
// https://vuejs.org/guide/essentials/list
// https://adventure-capitalist.fandom.com/wiki/Businesses
// css cover x until money balance is reaches a certain amount
// https://gaming.stackexchange.com/questions/330133/what-s-the-price-scaling-for-businesses
// https://vuejs.org/guide/essentials/class-and-style 