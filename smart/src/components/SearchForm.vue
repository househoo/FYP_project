<template>
    <section id="search">
      <h2>搜索酒店</h2>
      <form @submit.prevent="onSubmit">
        <input v-model="searchData.location" type="text" placeholder="城市或酒店名称" required>
        <input v-model="searchData.checkIn" type="date" placeholder="入住日期" required>
        <input v-model="searchData.checkOut" type="date" placeholder="退房日期" required>
        <select v-model="searchData.priceRange">
          <option value="">价格范围</option>
          <option value="budget">经济型</option>
          <option value="mid">中档</option>
          <option value="luxury">豪华</option>
        </select>
        <button type="submit">搜索</button>
      </form>
    </section>
  </template>
  
  <script setup>
  import { reactive } from 'vue';
  
  const searchData = reactive({
    location: '',
    checkIn: '',
    checkOut: '',
    priceRange: ''
  });
  
  const emit = defineEmits(['search']);
  
  function onSubmit() {
    emit('search', searchData);
  }
  </script>
  
  <style scoped>
  form {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin-bottom: 2rem;
  }
  input, select, button {
    padding: 0.5rem;
  }
  button {
    background-color: #4a90e2;
    border: none;
    color: white;
    cursor: pointer;
  }
  </style>