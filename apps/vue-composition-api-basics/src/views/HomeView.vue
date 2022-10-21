<template>
  <div class="home container mx-auto bg-gray-200 rounded-xl shadow border p-8 m-10">
    <h1 class="text-3xl text-gray-700 font-bold mb-5">Home</h1>
    <p class="text-gray-500 text-lg">
      This is the home page. You can use this page as a starting point for creating your own page.
    </p>
    <div class="mx-auto mt-10 max-w-sm sm:flex sm:max-w-none justify-center items-center flex-col">
      <div class="flex items-center mb-6">
        <h3 class="text-gray-700 text-lg font-bold">{{ counterData.title }}</h3>
      </div>
      <div class="space-y-4 sm:mx-auto sm:inline-grid sm:grid-cols-2 sm:gap-5 sm:space-y-0 mb-6">
        <button
          class="flex items-center justify-center rounded-md border border-transparent bg-white px-4 py-3 text-2xl font-medium text-indigo-700 shadow-sm hover:bg-indigo-50 sm:px-8"
          @click="decreaseCounter">
          -
        </button>
        <button
          class="flex items-center justify-center rounded-md border border-transparent bg-indigo-500 bg-opacity-60 px-4 py-3 text-2xl font-medium text-white shadow-sm hover:bg-opacity-70 sm:px-8"
          @click="increaseCounter">
          +
        </button>
      </div>
      <div class="space-y-4 sm:mx-auto sm:space-y-0 mb-6">
        <span
          class="counter flex items-center justify-center rounded-md border border-transparent bg-white px-4 py-3 text-2xl font-medium text-black shadow-sm sm:px-8">
          Count: {{ counterData.count }}
        </span>
      </div>
      <div class="space-y-4 sm:mx-auto sm:space-y-0 mb-12">
        <span
          class="counter flex items-center justify-center rounded-md border border-transparent bg-white px-4 py-3 text-2xl font-medium text-black shadow-sm sm:px-8">
          Count Doubled: {{ myComputedProperty }}
        </span>
      </div>
      <div class="edit">
        <label for="title" class="block text-sm font-medium text-gray-700">
          Edit Counter Title:
        </label>
        <div class="mt-1">
          <input
            id="title"
            v-model="counterData.title"
            type="text"
            name="title"
            class="block w-full rounded-md border-gray-300 p-2 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm"
            placeholder="Counter" />
        </div>
      </div>
    </div>
  </div>
</template>


//* SCRIPT SETUP PATTERN 
//* the new way
<script setup>
import { ref, reactive, computed, watch } from 'vue'

const counter = ref(0),
  counterTitle = ref('Counter')

const counterData = reactive({
  count: 0,
  title: 'Counter',
})

watch(
  () => counterData.count,
  (newCount, oldCount) => {
    // we have access to the new and old values of the property we are watching
    console.log('newCount', newCount)
    console.log('oldCount', oldCount)
  }
)

const myComputedProperty = computed(() => {
  const result = counterData.count * 2
  return result
})

const increaseCounter = () => {
  counterData.count++
}

const decreaseCounter = () => {
  counterData.count--
}
</script>
