<template>
  <div>
    <p class="flex justify-center text-lg mb-10">Ordered by {{ order }}</p>
    <transition-group name="list" tag="ul">
      <li class="card" v-for="music in orderedMusics" :key="music.id">
        <h4 class="text-2xl m-2">{{ music.title }}</h4>
        <img
          :src="music.cover"
          class="h-40 w-40 border-2 border-black hover:shadow-lg cursor-pointer"
        />
        <p class="text-sm m-2">From: {{ music.album }}</p>
        <p class="text-sm m-2">{{ music.year }}</p>
      </li>
    </transition-group>
  </div>
</template>

<script lang="ts">
import OrderTerm from "@/types/OrderTerm";
import { computed, defineComponent, PropType } from "vue";
import Musics from "../types/Musics";

export default defineComponent({
  props: {
    musics: {
      required: true,
      type: Array as PropType<Musics[]>,
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>,
    },
  },
  setup(props) {
    const orderedMusics = computed(() => {
      return [...props.musics].sort((a: Musics, b: Musics) => {
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
