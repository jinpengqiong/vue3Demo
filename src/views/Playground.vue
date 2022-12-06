<template>
  <div>{{ reactivePerson }}</div>
  <div>{{ toRawPerson }}</div>
  <button @click="update">按钮</button>
</template>
<script>
  import { reactive, toRaw } from 'vue';

  export default {
    setup() {
      const person = { name: '橙某人', age: 18 };
      const reactivePerson = reactive(person);
      const toRawPerson = toRaw(reactivePerson);

      console.log(person === toRawPerson); // true

      function update() {
        toRawPerson.name = 'YDYDYDQ';
        reactivePerson.name = '212123123'
        console.log(person, reactivePerson, toRawPerson);
      }

      return { reactivePerson, toRawPerson, update };
    }
  }
</script>