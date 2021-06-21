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
import Musics from "./types/Musics";
import OrderTerm from "./types/OrderTerm";
import MusicList from "./components/MusicList.vue";

export default defineComponent({
  name: "App",
  components: { MusicList },
  setup() {
    const musics = ref<Musics[]>([
      {
        title: "Freedom",
        album: "Rage Against The Machine",
        year: 1991,
        id: "1",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Killing in the name",
        album: "Rage Against The Machine",
        year: 1991,
        id: "2",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Bombtrack",
        album: "Rage Against The Machine",
        year: 1991,
        id: "3",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Tire Me",
        album: "Evil Empire",
        year: 1996,
        id: "4",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Vietnow",
        album: "Evil Empire",
        year: 1996,
        id: "5",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "People of the sun",
        album: "Evil Empire",
        year: 1996,
        id: "6",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Bulls on parade",
        album: "Evil Empire",
        year: 1996,
        id: "7",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Revolver",
        album: "Evil Empire",
        year: 1996,
        id: "8",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Snakecharmer",
        album: "Evil Empire",
        year: 1996,
        id: "9",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Down rodeo",
        album: "Evil Empire",
        year: 1996,
        id: "10",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Without a face",
        album: "Evil Empire",
        year: 1996,
        id: "11",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Wind below",
        album: "Evil Empire",
        year: 1996,
        id: "12",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Roll right",
        album: "Evil Empire",
        year: 1996,
        id: "13",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Year of tha boomerang",
        album: "Evil Empire",
        year: 1996,
        id: "14",
        cover:
          "https://www.tenhomaisdiscosqueamigos.com/wp-content/uploads/2016/03/Rage-Against-the-Machine-Evil-Empire.jpg",
      },
      {
        title: "Take the power back",
        album: "Rage Against The Machine",
        year: 1991,
        id: "15",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Bullet in the head",
        album: "Rage Against The Machine",
        year: 1991,
        id: "16",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Settle for nothing",
        album: "Rage Against The Machine",
        year: 1991,
        id: "17",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Know your enemy",
        album: "Rage Against The Machine",
        year: 1991,
        id: "18",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Wake up",
        album: "Rage Against The Machine",
        year: 1991,
        id: "19",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Fistfull of steel",
        album: "Rage Against The Machine",
        year: 1991,
        id: "20",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Township Rebelion",
        album: "Rage Against The Machine",
        year: 1991,
        id: "19",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
      },
      {
        title: "Freedom",
        album: "Rage Against The Machine",
        year: 1991,
        id: "20",
        cover:
          "https://upload.wikimedia.org/wikipedia/pt/2/2a/RageAgainstTheMachine.jpg",
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
