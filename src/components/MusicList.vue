<template>
  <div>
    <p>Ordered by {{ order }}</p>
    <ul>
      <li v-for="music in orderedMusics" :key="music.id">
        <h2>{{ music.title }}</h2>
        <h4>From: {{ music.album }}</h4>
        <h4>{{ music.year }}</h4>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import OrderTerm from "@/types/OrderTerm";
import { computed, defineComponent, PropType } from "vue";
import Music from "../types/Music";

export default defineComponent({
  props: {
    musics: {
      required: true,
      type: Array as PropType<Music[]>,
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>,
    },
  },
  setup(props) {
    const orderedMusics = computed(() => {
      return [...props.musics].sort((a: Music, b: Music) => {
        return a[props.order] > b[props.order] ? 1 : -1;
      });
    });
    return { orderedMusics };
  },
});
</script>

<style>
</style>
