<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('Alina')">changeName</button>
    <button @click="changeAge('23')">changeName</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  components: {},

  data() {
    return {
      name: 'link',
      age: 25 as number | string,
    };
  },

  methods: {
    changeName(name: string) {
      this.name = name;
    },

    changeAge(age: string) {
      this.age = age;
    },
  },
});
</script>

<style></style>
