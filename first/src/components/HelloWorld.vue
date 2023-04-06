<script setup>
import { ref, reactive, toRefs } from 'vue'

defineProps({
  msg: String
})

// ref 使数据可以响应式
const count = ref(0)

// reactive 定义引用类型的数据 例：obj
const obj = reactive({
  name: '张三', age: 18
})
function nameChange() {
  obj.name = '李四1';
}
// toRefs：解构赋值
let {name} = toRefs(obj)

</script>

<template>
  <button @click="nameChange()">{{ msg }} -- 我叫 -- {{ obj.name }}</button>
  <button @click="nameChange()">{{ msg }} -- 我叫 -- {{ name }}</button>
  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
  </div>

</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
