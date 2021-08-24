<template>
  <h1>{{ msg }}</h1>

  <button type="button" @click="state.count++">
    count is: {{ state.count }}
  </button>
  <div class="home">
    这里是一个计数器 <span class="red">{{ count }}</span> <br />
    <button @click="countAdd">{{ btnText }}</button>
  </div>
</template>

<script setup>
import { defineProps, reactive } from "vue";

defineProps({
  msg: String,
});

const state = reactive({ count: 0 });
import { ref } from "vue";
// 导出依然是个对象，不过对象中只有一个 setup 函数

// 定义一个不需要改变的数据
const btnText = "点这个按钮上面的数字会变";
// 定义一个 count 的响应式数据，并赋值为 0
const count = ref(0);
// 定义一个函数，修改 count 的值。
const countAdd = () => {
  count.value++;
};
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
