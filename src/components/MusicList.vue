<template>
  <div>
    <p class="flex justify-center text-lg mb-10">Ordered by {{ order }}</p>
    <transition-group name="list" tag="ul">
      <li class="card" v-for="music in orderedMusics" :key="music.id">
        <h4 class="text-2xl m-2">{{ music.title }}</h4>
        <p>From: {{ music.album }}</p>
        <p>{{ music.year }}</p>
      </li>
    </transition-group>
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
.list-move {
  transition: all 1s;
}
</style>
