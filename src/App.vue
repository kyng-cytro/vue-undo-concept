<template>
  <div class="h-screen lg:max-w-4xl mx-auto text-slate-200 max-h-screen">
    <!-- Header -->
    <div
      class="h-[15%] flex flex-col items-center justify-center bg-slate-500 w-full space-y-3 border-b-2 border-black"
    >
      <h1 class="text-xl font-semibold">Point Plotter</h1>
      <p class="text-slate-300">
        Use
        <kbd
          class="px-2 py-1.5 text-xs font-semibold text-gray-200 bg-gray-500 border border-gray-600 rounded-lg"
          >Ctrl</kbd
        >
        +
        <kbd
          class="px-2 py-1.5 text-xs font-semibold text-gray-200 bg-gray-500 border border-gray-600 rounded-lg"
          >Z</kbd
        >
        to undo &
        <kbd
          class="px-2 py-1.5 text-xs font-semibold text-gray-200 bg-gray-500 border border-gray-600 rounded-lg"
          >Ctrl</kbd
        >
        +
        <kbd
          class="px-2 py-1.5 text-xs font-semibold text-gray-200 bg-gray-500 border border-gray-600 rounded-lg"
          >Y</kbd
        >
        to redo
      </p>
    </div>
    <!-- Plotter -->
    <div class="bg-slate-200 h-[70%] w-full"></div>
    <!--Footer-->
    <div
      class="h-[15%] flex flex-col items-center justify-center bg-slate-500 w-full border-t-2 border-black sm:gap-3"
    >
      <span class="text-sm text-gray-200 sm:text-center">
        <a href="https://flowbite.com/" class="hover:underline">Cytro</a> with
        love
      </span>
      <ul class="flex flex-wrap items-center mt-3 text-sm text-gray-200">
        <li>
          <a href="#" class="mr-4 hover:underline md:mr-6">Github</a>
        </li>
        <li>
          <a href="#" class="mr-4 hover:underline md:mr-6">Twitter</a>
        </li>
        <li>
          <a href="#" class="mr-4 hover:underline md:mr-6">Linkedin</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts"></script>
<style scoped></style>
