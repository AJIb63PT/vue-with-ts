<template>
  <div class="app">
    <header>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('salary')">order by salary</button>
        <button @click="handleClick('location')">order by location</button>
      </div>
    </header>
    <jobList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import Job from './types/job';
import orderTerm from './types/orderTerm';

import jobList from './components/jobList.vue';
export default defineComponent({
  name: 'App',
  components: { jobList },
  setup() {
    const jobs = ref<Job[]>([
      { title: 'farmworker', location: 'lon ranch', salary: 1200, id: '1' },
      { title: 'jun frontend', location: 'yandex', salary: 1500, id: '2' },
      { title: 'midl frontend', location: 'twitch', salary: 2000, id: '3' },
      {
        title: 'senior frontend ',
        location: 'google',
        salary: 2533,
        id: '4',
      },
      {
        title: 'genius frontend ',
        location: 'tesla',
        salary: 5000,
        id: '5',
      },
    ]);
    const order = ref<orderTerm>('title');
    const handleClick = (term: orderTerm) => {
      order.value = term;
    };
    return { jobs, handleClick, order };
  },

  data() {
    return {};
  },
});
</script>

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
