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
        to undo ,
        <kbd
          class="px-2 py-1.5 text-xs font-semibold text-gray-200 bg-gray-500 border border-gray-600 rounded-lg"
          >Ctrl</kbd
        >
        +
        <kbd
          class="px-2 py-1.5 text-xs font-semibold text-gray-200 bg-gray-500 border border-gray-600 rounded-lg"
          >Y</kbd
        >
        to redo &
        <kbd
          class="px-2 py-1.5 text-xs font-semibold text-gray-200 bg-gray-500 border border-gray-600 rounded-lg"
          >Ctrl</kbd
        >
        +
        <kbd
          class="px-2 py-1.5 text-xs font-semibold text-gray-200 bg-gray-500 border border-gray-600 rounded-lg"
          >X</kbd
        >
        to clear
      </p>
    </div>
    <!-- Plotter -->
    <div @click="addPoint" class="bg-slate-200 h-[70%] w-full relative">
      <GlobalEvents @keyup.ctrl="undo_redo" />
      <div
        :style="{ top: `${point.y}px`, left: `${point.x}px` }"
        class="w-4 h-4 rounded-full bg-slate-700 absolute"
        v-for="(point, index) in points"
        :key="index"
      ></div>
    </div>
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

<script setup lang="ts">
import { ref } from "vue";
import { GlobalEvents } from "vue-global-events";

interface Point {
  x: Number;
  y: Number;
}
let points = ref<Array<Point>>([]);
let deleted = ref<Array<Point>>([]);

const addPoint = (e: MouseEvent) => {
  const point = <Point>{
    x: e.offsetX,
    y: e.offsetY,
  };
  points.value.push(point);
};

const undo_redo = (e: KeyboardEvent) => {
  if (e.key == "z") {
    if (points.value.length > 0) {
      deleted.value.push(points.value.pop() as Point);
    }
  } else if (e.key == "y") {
    if (deleted.value.length > 0) {
      points.value.push(deleted.value.pop() as Point);
    }
  } else if (e.key == "x") {
    points.value = [];
    deleted.value = [];
  }
};
</script>
<style scoped></style>
