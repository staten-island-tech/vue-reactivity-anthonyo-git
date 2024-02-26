<template> 
  <div class="overlay" @click="close">
    <div class="content" @click.stop>
      <button class="closeBTN" @click="close">X</button>
      <button @click="toggleAchievements">Toggle Achievements</button>
      <h2>Achievements</h2>
      <div v-if="showAchievements">
        <h3>>1000000000</h3>
        <h3>>100000000000</h3>
        <h3>>100000000000000</h3>
        <h3>>1000000000000000000</h3>
        <h3>>100000000000000000000000</h3>
      </div>
    </div>
  </div>
</template>








<script>

</script>

<style scoped> 



</style>