<template>
  <div class="app">
    <header class="relative bg-white">
      <div class="mx-auto max-w-7xl px-4 sm:px-6">
        <nav
          class="flex items-center justify-between border-b-2 border-gray-100 py-6 md:justify-start md:space-x-10"
        >
          <RouterLink
            class="text-lg text-blue-600 hover:text-black active:text-green-600 visited:text-red-600"
            to="/"
            >Home</RouterLink
          >
          <RouterLink
            class="text-lg text-blue-600 hover:text-black active:text-green-600 visited:text-red-600"
            to="/about"
            >About</RouterLink
          >
        </nav>
      </div>
    </header>
    <main class="mx-auto max-w-7xl px-4 sm:px-6">
      <RouterView />
    </main>
  </div>
</template>
