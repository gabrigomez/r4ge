<template>
  <div class="text-lg font-body">
    <header>
      <div class="flex justify-center items-center">
        <i class="hidden lg:block px-2">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-8 w-8 text-red-600"
            viewBox="0 0 20 20"
            fill="currentColor"
          >
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            />
          </svg>
        </i>
        <h1 class="text-7xl flex justify-center">RAGE AGAINST THE MACHINE</h1>
        <i class="hidden lg:block p-2">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-8 w-8 text-red-600"
            viewBox="0 0 20 20"
            fill="currentColor"
          >
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            />
          </svg>
        </i>
      </div>
      <p class="text-lg flex justify-center">Music bio</p>
    </header>
    <div class="flex justify-center m-10">
      <button class="btn" @click="handleClick('title')">Order by title</button>
      <button class="btn" @click="handleClick('album')">Order by album</button>
      <button class="btn" @click="handleClick('year')">Order by year</button>
    </div>
    <MusicList :musics="musics" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Music from "./types/Music";
import OrderTerm from "./types/OrderTerm";
import MusicList from "./components/MusicList.vue";

export default defineComponent({
  name: "App",
  components: { MusicList },
  setup() {
    const musics = ref<Music[]>([
      {
        title: "Freedom",
        album: "Rage Against The Machine",
        year: 1991,
        id: "1",
      },
      {
        title: "Killing in the name",
        album: "Rage Against The Machine",
        year: 1991,
        id: "2",
      },
      {
        title: "Bombtrack",
        album: "Rage Against The Machine",
        year: 1991,
        id: "3",
      },
      {
        title: "Tire Me",
        album: "Evil Empire",
        year: 1996,
        id: "4",
      },
    ]);

    const order = ref<OrderTerm>("title");

    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };

    return { musics, handleClick, order };
  },
});
</script>

<style>
</style>
