<script setup>
import { ref } from 'vue'

const page = ref(1)

const onClickPrev = (n) => {
  console.log(n);
}

const onClickNext = (n) => {
  console.log(n);
}
</script>

<template>
  <main>
    <!-- basic -->
    <v-pagination :length="4"></v-pagination>

    <!-- props -->
    <v-pagination :length="4" active-color="red"></v-pagination>

    <!-- events -->
    <v-pagination :length="4" @prev="onClickPrev" @next="onClickNext"></v-pagination>

    <!-- slot -->
    <v-pagination v-model="page" :length="4">
      <template #next="{ onClick, disabled }">
        <div v-show="!disabled">
          <button @click="onClick">
            <p>Next</p>
            <span class="mdi mdi-chevron-right" />
          </button>
        </div>
      </template>
      <template #prev="{ onClick, disabled }">
        <div v-show="!disabled">
          <button @click="onClick">
            <p>Prev</p>
            <span class="mdi mdi-chevron-left" />
          </button>
        </div>
      </template>
    </v-pagination>

  </main>
</template>

<style scoped>
main {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
