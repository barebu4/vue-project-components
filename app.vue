<script setup>
  import { ref } from 'vue';
  import ChildItem from './components/ChildItem.vue';

  let userNames = ref(["Ivan"])

  function addNames(){
    userNames.value.push("")
    // console.log(userNames.value)
  }
</script>

<template>
  <h1>Users list</h1>
  <h3>Add User</h3>
  <button @click="addNames">Add user</button>
  <div v-for="(name, index) in userNames" :key="index">
    <ChildItem v-model="userNames[index]"/>
  </div>
  <ul>
    <li v-for="(name, index) in userNames" :key="index">{{ name }} </li>
  </ul>
</template>