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
    </div>
  </div>
</template>


//* SCRIPT SETUP PATTERN 
//* the new way
<script setup>
import { ref } from 'vue'

const counter = ref(0)

const increaseCounter = () => {
  counter.value++
}

const decreaseCounter = () => {
  counter.value--
}
</script>


//* SETUP FUNCTION PATTERN
//* the old way


//   <script>
// import { ref } from 'vue'

// export default {
//   setup() {
//     // DATA
//     const counter = ref(0)

//     // METHODS
//     const increaseCounter = () => {
//       counter.value++
//     }

//     const decreaseCounter = () => {
//       counter.value--
//     }

//     // RETURN
//     return {
//       counter,
//       increaseCounter,
//       decreaseCounter,
//     }
//   },
// }
//
// eslint-disable-next-line
// </script>
