<script setup>
// 在 setup 中你应该避免使用 this，因为它不会找到组件实例。
// setup 的调用发生在 data property、computed property 或 methods 被解析之前，所以它们无法>在 setup 中被获取。
import TheWelcome from '../components/TheWelcome.vue'
import { useCounterStore } from '@/stores/counter'
const counterStore = useCounterStore()
function handleClick() {
  counterStore.increment()
}
</script>
<template>
    <main>
        <TheWelcome />
        {{counterStore.doubleCount}}
        <button @click="handleClick">click it</button>
    </main>
</template>
