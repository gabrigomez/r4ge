<template>
  <div>
    <ul>
      <li v-for="music in musics" :key="music.id">
        <h2>{{ music.title }}</h2>
        <h4>From: {{ music.album }}</h4>
        <h4>{{ music.year }}</h4>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import Music from "../types/Music";

export default defineComponent({
  props: {
    musics: {
      require: true,
      type: Array as PropType<Music[]>,
    },
  },
});
</script>

<style>
</style>
