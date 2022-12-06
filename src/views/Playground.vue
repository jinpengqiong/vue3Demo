<template>
  <div>{{person}}</div>
  <button @click="update1">按钮一</button>
  <button @click="update2">按钮二</button>
</template>

<script>
  import { shallowRef, shallowReactive,toRef } from 'vue'
  export default {
    setup() {
      const person = shallowRef({
        name: '橙某人',
      });

      function update1() {
        console.log('person', person)
        person.value.name = 'YDYDYDQ';
        console.log(person.value); // {name: 'YDYDYDQ'}
      }

      function update2() {
        person.value = {
          name: 'ydydydq'
        };
        console.log(person.value); // {name: 'ydydydq'}
      }

      return { person, update1, update2 };
    }
  }
</script>