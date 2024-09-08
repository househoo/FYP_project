<template>
    <div id="app">
      <Header />
      <main>
        <SearchForm @search="searchHotels" />
        <SearchResults :hotels="hotels" @book="bookHotel" />
        <Bookings />
        <Account />
      </main>
      <Footer />
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import Header from './components/Header.vue';
  import SearchForm from './components/SearchForm.vue';
  import SearchResults from './components/SearchResults.vue';
  import Bookings from './components/Bookings.vue';
  import Account from './components/Account.vue';
  import Footer from './components/Footer.vue';
  
  const hotels = ref([
    { id: 1, name: "豪华大酒店", price: 888, rating: 4.5 },
    { id: 2, name: "舒适旅馆", price: 388, rating: 4.0 },
    { id: 3, name: "经济型酒店", price: 188, rating: 3.5 },
  ]);
  
  function searchHotels(searchData) {
    console.log('搜索数据:', searchData);
    // 这里应该发送API请求获取真实数据
    // 现在我们使用模拟数据，实际应用中应该更新hotels ref
  }
  
  function bookHotel(hotelId) {
    alert(`您已成功预订ID为${hotelId}的酒店！`);
    // 这里应该发送API请求进行实际的预订操作
  }
  </script>
  
  <style>
  body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
  }
  main {
    padding: 2rem;
  }
  </style>