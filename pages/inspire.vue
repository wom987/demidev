<template>
  <v-container>
    <h1 class="text-center">Counter Example</h1>
    <v-row class="mt-5 pt-5">
      <v-col class="text-center">
        <v-container>
          <h3 class="text-center">Count is {{ store.count }}</h3>
          <h3 class="text-center">Double is {{ store.doubleCount }}</h3>
        </v-container>
        <v-btn @click="store.increment(1)" elevation="2" color="primary"
          >Increment</v-btn
        >
        <v-btn @click="store.waitAndAdd" elevation="2" color="primary"
          >Wait + Increment</v-btn
        >
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { useCounterStore } from '~/store/counter'
const store = useCounterStore()
//store.count++
//store.increment(2)
</script>
