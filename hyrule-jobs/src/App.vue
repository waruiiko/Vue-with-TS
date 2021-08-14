<template>
  <div class="app">
    <header>
      <div class="order">
        <!-- <jobs-list  /> -->
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('salary')">order by salary</button>
        <button @click="handleClick('location')">order by location</button>
      </div>
    </header>
    <JobsList :jobs="jobs" :order="order" />
    <!-- <h1>{{ name }}-{{ age }}</h1>
    <input v-model="anotherName" />
    <input v-model="anotherAge" />
    <button @click="changeName">changeName</button>
    <button @click="changeAge">changeAge</button> -->
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Job from "./types/Job";
import OrderTerm from "./types/OrderTerm";
import JobsList from "./components/JobsList.vue";

export default defineComponent({
  name: "App",
  components: { JobsList },
  setup() {
    //reactive
    // const state = reactive({
    //   name: "xiaoming",
    //   age: 30 as string | number,
    //   anotherName: "",
    //   anotherAge: "",
    // });
    // //对象展开运算符
    // return {... toRefs(state)}

    // //ref
    // const name = ref('xiaoming');
    // const age = ref<number|string>(25);
    // const anotherName = ref('')
    // const anotherAge = ref('')

    // return {name, age, anotherName, anotherAge}

    const jobs = ref<Job[]>([
      { title: "xiaoming", location: "xiaoming", salary: 10000, id: "1" },
      { title: "ss", location: "SS", salary: 60000, id: "2" },
      { title: "C", location: "ZC", salary: 30000, id: "3" },
      { title: "m", location: "m", salary: 70000, id: "4" },
      { title: "E", location: "GE", salary: 50000, id: "5" },
    ]);

    const order = ref<OrderTerm>("title");
    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };

    return { jobs, order, handleClick };
  },
  // data() {
  //   return {
  //     name: "xiaoming",
  //     age: 30 as string | number,
  //     anotherName: "",
  //     anotherAge: "",
  //   };
  // },
  methods: {
    // changeName() {
    //   this.name = this.anotherName;
    //   return;
    // },
    // changeAge() {
    //   this.age = this.anotherAge;
    //   return;
    // },
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
