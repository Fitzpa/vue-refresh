<template>
  <div class="home container mx-auto bg-gray-200 rounded-xl shadow border p-8 m-10">
    <h1 class="text-3xl text-gray-700 font-bold mb-5">Home</h1>
    <p class="text-gray-500 text-lg">
      This is the home page. You can use this page as a starting point for creating your own page.
    </p>
    <div class="mx-auto mt-10 max-w-sm sm:flex sm:max-w-none justify-center items-center flex-col">
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
      <div class="space-y-4 sm:mx-auto sm:space-y-0">
        <span
          class="counter flex items-center justify-center rounded-md border border-transparent bg-white px-4 py-3 text-2xl font-medium text-black shadow-sm sm:px-8">
          {{ counter }}
        </span>
      </div>
      <div class="space-y-4 sm:mx-auto sm:space-y-0">
        <span
          class="counter flex items-center justify-center rounded-md border border-transparent bg-white px-4 py-3 text-2xl font-medium text-black shadow-sm sm:px-8">
          {{ myComputedProperty }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
// IMPORTS
export default {
  data() {
    return {
      counter: 0,
    }
  },
  computed: {
    myComputedProperty() {
      // A computed property is a property that is calculated based on other properties
      // perform some computation based on the data
      const result = this.counter * 2
      return result
    },
  },
  watch: {
    counter(newCount, oldCount) {
      // watcher name is the name of the property we want to watch
      // A watch is a property that is triggered when a property changes
      // perform some action when the data changes
      if (newCount === 5) {
        console.log('You reached 5!')
        alert('Count is now 5!')
      }
      if (oldCount === 5) {
        console.log('You left 5!')
        alert('Count is no longer 5!')
      }
    },
  },
  mounted() {
    // A lifecycle hook is a function that is called at a specific point in the lifecycle of a component
    // perform some action when the component is mounted
    console.log('Mounted!')
  },
  unmounted() {
    // A lifecycle hook is a function that is called at a specific point in the lifecycle of a component
    // perform some action when the component is unmounted
    console.log('Unmounted!')
  },
  methods: {
    increaseCounter() {
      this.counter++
    },
    decreaseCounter() {
      this.counter--
    },
  },
}
</script>