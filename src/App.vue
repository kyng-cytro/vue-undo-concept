<template>
  <div class="h-screen lg:max-w-4xl mx-auto text-slate-200 max-h-screen">
    <!-- Header -->
    <div
      class="h-[15%] flex flex-col items-center justify-center bg-slate-500 w-full space-y-3 border-b-2 border-black"
    >
      <h1 class="text-xl font-semibold">Point Plotter</h1>
      <p class="text-slate-300">
        Use Ctrl + Z to undo plot & Ctrl + Y to redo plot
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
