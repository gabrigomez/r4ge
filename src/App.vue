<template>
  <div class="app">
    <h1>RAGE AGAINST THE MACHINE</h1>
    <header>
      <div>
        <button @click="handleClick('title')">Order by title</button>
        <button @click="handleClick('album')">Order by album</button>
        <button @click="handleClick('year')">Order by year</button>
      </div>
    </header>
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
