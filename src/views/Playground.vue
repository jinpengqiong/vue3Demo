<template>
  <div id="box">
    <p>id选择器</p>
  </div>
  <div class="box">
    <p>class选择器</p>
  </div>
  <div data-box>
    <p>class选择器</p>
  </div>
  <!--teleport-->
  <teleport :to="target">
    <h2>橙某人</h2>
  </teleport>
  <div>
    <button @click="update('body')">传送到body中</button>
    <button @click="update('#box')">传送到id选择器中</button>
    <button @click="update('.box')">传送到class选择器中</button>
    <button @click="update('[data-box]')">传送到属性选择器中</button>
  </div>
</template>

<script>
  import { ref } from 'vue';
  export default {
    setup() {
      const target = ref('#app'); // 初始化渲染的位置

      function update(selector) {
        target.value = selector;
      }

      return { target, update }
    }
  }
</script>