<template>
  <p>
    {{ music[0] }}
  </p>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Music from "./types/Music";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    const music = ref<Music[]>([
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

    return { music };
  },
  methods: {},
});
</script>

<style>
</style>
