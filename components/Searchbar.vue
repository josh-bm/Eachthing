<script setup></script>

<template>
  <div>
    <form class="flex items-center w-full">
      <label for="simple-search" class="sr-only">Search</label>
      <div class="relative w-full">
        <div
          class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none"
        >
          <svg
            class="w-5 h-5 text-black"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
              clip-rule="evenodd"
            ></path>
          </svg>
        </div>
        <input
          type="search"
          id="simple-search"
          class="border border-gray-50 placeholder:text-black rounded-lg block w-full pl-10 p-2.5"
          placeholder="What are you looking for today?"
          required
        />
      </div>
      <nuxt-link to="/search">
        <button
          type="submit"
          class="p-2.5 ml-2 text-sm font-medium text-white bg-teal-800 rounded-lg shadow-lg border border-teal-800 hover:bg-teal-900"
        >
          <svg
            class="w-5 h-5"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
            ></path>
          </svg>
        </button>
      </nuxt-link>
    </form>
  </div>
</template>

<style></style>
