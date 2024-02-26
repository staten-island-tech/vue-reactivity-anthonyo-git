<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue';

const showOverlay = ref(false);
</script>

<template>
  <div class="body">
    <div class="wrapper">
      <nav>
      </nav>
    </div>
  <RouterView />
  </div>
</template>


<style scoped></style>


