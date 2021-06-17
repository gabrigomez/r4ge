<template>
  <div class="app">
    <h1>RAGE AGAINST THE MACHINE</h1>
    <MusicList :musics="musics" />
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Music from "./types/Music";
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
    ]);

    return { musics };
  },
  methods: {},
});
</script>

<style>
</style>
