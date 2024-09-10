<template>
    <section id="results">
      <h2>搜索结果</h2>
      <div v-for="hotel in hotels" :key="hotel.id" class="hotel-card">
        <h3>{{ hotel.name }}</h3>
        <p>价格: ¥{{ hotel.price }}/晚</p>
        <p>评分: {{ hotel.rating }}/5</p>
        <button @click="$emit('book', hotel.id)">预订</button>
      </div>
    </section>
  </template>
  
  <script setup>
  defineProps(['hotels']);
  defineEmits(['book']);
  </script>
  
  <style scoped>
  #results {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
  }
  .hotel-card {
    border: 1px solid #ddd;
    border-radius: 4px;
    padding: 1rem;
    width: calc(33.33% - 1rem);
  }
  </style>