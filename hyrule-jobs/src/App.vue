<template>
  <div class="app">
    hello hyrule
    <!-- <jobs-list  /> -->
    <JobsList :jobs="jobs" />
    <!-- <h1>{{ name }}-{{ age }}</h1>
    <input v-model="anotherName" />
    <input v-model="anotherAge" />
    <button @click="changeName">changeName</button>
    <button @click="changeAge">changeAge</button> -->
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive,ref,toRefs } from "vue";
import './types/Job'
import Job from "./types/Job";
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
      {title:'A',location:'AddressA',salary:10000,id:'1'},
      {title:'B',location:'AddressB',salary:20000,id:'2'},
      {title:'C',location:'AddressC',salary:30000,id:'3'},
      {title:'D',location:'AddressD',salary:40000,id:'4'},
      {title:'E',location:'AddressE',salary:50000,id:'5'}
    ])
    return {jobs}
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
</style>
