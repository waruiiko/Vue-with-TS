<template>
  <div class="app">
    hello hyrule
    <h1>{{name}}-{{age}}</h1>
    <input v-model="anotherName">
    <input v-model="anotherAge">
    <button @click="changeName">changeName</button>
    <button @click="changeAge">changeAge</button>
  </div>
  
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  data() {
    return {
      name: "xiaoming",
      age: 30 as string | number,
      anotherName:'',
      anotherAge:''
    };
  },
  methods: {
    changeName() {
      this.name = this.anotherName;
      return
    },
    changeAge() {
      this.age = this.anotherAge;
      return
    },
  },
});
</script>

<style>
</style>
