<template>
  <div>
    <button @click="update1">按钮1</button>
    <button @click="update2">按钮2</button>
  </div>
</template>

<script>
  import { ref, watchEffect } from 'vue';
  export default {
    setup() {
      const name = ref('橙某人');
      const age = ref(18);

      watchEffect(() => {
        console.log('**********');
        console.log(name.value);
        console.log(age.value);
      });

      function update1() {
        name.value = 'YDYDYDQ';
      }
      function update2() {
        age.value = 20;
      }

      return { update1, update2 }
    }
  }
</script>