<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div>
      <h5>{{counterStore.count}}</h5>
      <button @click="counterStore.increment">{{counterStore.doubleCount}}</button>
    </div>
  </div>
</template>

<script setup lang="ts">
  import { useCounterStore } from "../stores/counter.ts";
  const counterStore = useCounterStore()
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}
</style>
