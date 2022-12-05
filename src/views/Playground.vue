<template>
  <div>
    <div>昵称: {{person.name}}</div>
    <div>年龄: {{person.age}}</div>
    <!-- <div>昵称: {{name}}</div>
    <div>年龄: {{age}}</div> -->
    <button @click="update">按钮</button>
  </div>
</template>

<script>
  import { ref, watch, reactive } from 'vue';
  export default {
    setup() {
      const name = ref('橙某人');
      const age = ref(18);
      const person = reactive({
        name: '橙某人',
        age: 18
      });

      watch([() => person.name, () => person.age], (newValue, oldValue) => {
        console.log(newValue, oldValue);
      });

      function update() {
        person.value.name = 'YDYDYDQ';
        // person.age = 20;
      }

      return { person, name, age, update }
    }
  }
</script>
