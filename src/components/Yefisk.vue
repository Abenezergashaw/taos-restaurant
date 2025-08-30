<script setup>
import { ref, computed } from "vue";
import tibs from "../assets/tibs.jpeg";
import gebaweta from "../assets/gebaweta.jpeg";
import quanta from "../assets/quanta.jpeg";
import goat from "../assets/goat.jpeg";

const getImage = (index) => {
  return index === 0
    ? tibs
    : index === 1
    ? gebaweta
    : index === 2
    ? quanta
    : goat;
  // return tibs;
};
const yefisk = ref([
  {
    name: "ሩብ",
    price: 400,
    mini: 1,
    category: "APPETIZERS",
    description: "Assorted cocktail appetizers",
  },
  {
    name: "ግማሽ",
    price: 800,
    mini: 1,
    category: "APPETIZERS",
    description: "Crispy chicken nuggets with dipping sauce",
  },
  {
    name: "ሩብ ጉዳይ",
    price: 1200,
    mini: 1,
    category: "APPETIZERS",
    description: "Mini sandwiches with assorted fillings",
  },
  {
    name: "ኪሎ",
    price: 1400,
    mini: 1,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },

  {
    name: "ክትፎ",
    price: 500,
    mini: 1,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ሩብ ሙስና",
    price: 450,
    mini: 2,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ግማሽ ሙስና",
    price: 800,
    mini: 2,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ሩብ ገባ ወጣ",
    price: 400,
    mini: 2,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ግማሽ ገባ ወጣ",
    price: 800,
    mini: 2,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ግማሽ ብራውን",
    price: 1000,
    mini: 2,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ስጋ ፍርፍር",
    price: 400,
    mini: 3,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ጥብስ ፍርፍር",
    price: 400,
    mini: 3,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "እንቁላል በስጋ",
    price: 450,
    mini: 3,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ቋንጣ ፍርፍር",
    price: 450,
    mini: 3,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ምጣድ ጥብስ",
    price: 1600,
    mini: 3,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "የፍየል ጥብስ",
    price: 500,
    mini: 4,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ግማሽ(የፍየል)",
    price: 1000,
    mini: 4,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ሩብ ጉዳይ(የፍየል)",
    price: 1500,
    mini: 4,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
  {
    name: "ኪሎ(የፍየል)",
    price: 1600,
    mini: 4,
    category: "APPETIZERS",
    description: "Golden crispy fries with seasoning",
  },
]);
const isSpecial = ref(false);

const specials = ref([
  {
    name: "ታኦስ ፋሚሊ",
    price: 1800,
    category: "APPETIZERS",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ስፔሻል ጥብስ",
    price: 1200,
    category: "APPETIZERS",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ስፔሻል ክትፎ",
    price: 700,
    category: "APPETIZERS",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ታኦስ በጋራ",
    price: 2000,
    category: "APPETIZERS",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ትኑር ጎንደር ልዩ",
    price: 2000,
    category: "APPETIZERS",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ሀፍ ሀፍ",
    price: 800,
    category: "APPETIZERS",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ስፔሻል ሀፍ ሀፍ",
    price: 2000,
    category: "APPETIZERS",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
]);

// const filteredItems = computed(() =>
//   menuItems.filter((item) => item.category === activeCategory.value.name)
// );
// const chunkedItems = computed(() => {
//   const chunks = [];
//   for (let i = 0; i < yefisk.value.length; i += 5) {
//     chunks.push(yefisk.value.slice(i, i + 5));
//   }
//   return chunks;
// });
const chunkedItems = computed(() => {
  const groups = {};
  yefisk.value.forEach((item) => {
    if (!groups[item.mini]) {
      groups[item.mini] = [];
    }
    groups[item.mini].push(item);
  });
  return Object.values(groups);
});
</script>

<template>
  <div
    class="text-white text-center tracking-widest uppercase font-bold text-base my-2 flex gap-2 justify-center"
  >
    <button
      v-if="isSpecial"
      @click="isSpecial = false"
      class="flex items-center gap-2 px-3 py-0.5 rounded-lg bg-gray-200 hover:bg-gray-300 text-gray-700 font-medium text-xs"
    >
      Back
    </button>
    <div class="flex gap-2" @click="isSpecial = true">
      <div class="text-yellow-300">
        {{ isSpecial ? "ስፔሻል ምግቦች" : "ስፔሻል ምግቦችን ይመልከቱ" }}
      </div>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="20"
        height="20"
        fill=""
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="lucide lucide-utensils text-yellow-400"
      >
        <path d="M4 3h1v18H4zM9 3h1v7a3 3 0 0 1-6 0V3h1" />
        <path d="M15 3c0 3.31-2.69 6-6 6h6c0-3.31 2.69-6 6-6h-6Z" />
      </svg>
    </div>
  </div>

  <div
    v-if="isSpecial"
    class="grid grid-cols-2 gap-x-6 gap-y-4 w-full max-w-3xl mx-auto"
  >
    <div
      v-for="(item, index) in specials"
      :key="item.name"
      class="flex justify-between items-center px-3 py-2 rounded-xl shadow-sm transition transform hover:scale-105 hover:shadow-md"
      :class="
        index % 2 === 0
          ? 'bg-gradient-to-r from-gray-400 via-[#8f6c44]/20 to-[#d37c17]/20'
          : 'bg-gradient-to-r from-[#d37c17]/20 via-[#8f6c44]/20 to-gray-400'
      "
    >
      <!-- Name -->
      <span
        class="font-bold text-transparent bg-clip-text bg-gradient-to-r from-gray-200 via-[#a19587] to-[#d37c17]"
      >
        {{ item.name }}
      </span>
      <!-- Price -->
      <span
        class="font-bold text-transparent bg-clip-text bg-gradient-to-r from-[#d37c17] via-[#8f6c44] to-gray-200"
      >
        {{ item.price }} Br
      </span>
    </div>
  </div>
  <div v-if="!isSpecial">
    <div
      v-for="(group, index) in chunkedItems"
      :key="index"
      class="flex justify-between items-center text-white my-6"
    >
      <!-- Odd groups (index 0,2,4...) => list left, circle right -->
      <template v-if="index % 2 === 0">
        <div class="w-[53%] text-sm">
          <div
            v-for="item in group"
            :key="item.name"
            class="flex justify-between gap-3 items-center mb-2"
          >
            <div
              class="font-bold tracking-wider text-transparent bg-clip-text bg-gradient-to-r from-gray-200 via-[#8f6c44] to-[#d37c17] truncate"
              :style="{
                fontSize: `14px`,
              }"
            >
              {{ item.name }}
            </div>
            <div
              class="font-bold tracking-wider text-transparent bg-clip-text bg-gradient-to-r from-[#d37c17] via-[#8f6c44] to-gray-200"
            >
              {{ item.price }} Br
            </div>
          </div>
        </div>
        <div
          class="w-[45%] aspect-square rounded-tl-full rounded-bl-full bg-[#F78400] flex justify-center items-center"
        >
          <div class="w-[95%] aspect-square bg-[#322c2c] rounded-full">
            <img :src="getImage(index)" alt="" class="h-[100%] rounded-full" />
          </div>
        </div>
      </template>

      <!-- Even groups (index 1,3,5...) => circle left, list right -->
      <template v-else>
        <div
          class="w-[45%] aspect-square rounded-tr-full rounded-br-full bg-[#F78400] flex justify-center items-center"
        >
          <div
            class="w-[95%] aspect-square bg-[#322c2c] rounded-full flex justify-center items-center"
          >
            <img :src="getImage(index)" alt="" class="h-[100%] rounded-full" />
          </div>
        </div>
        <div class="w-[53%] text-sm">
          <div
            v-for="item in group"
            :key="item.name"
            class="flex justify-between items-center mb-2"
          >
            <div
              class="font-bold tracking-wider text-transparent bg-clip-text bg-gradient-to-r from-gray-200 via-[#8f6c44] to-[#d37c17]"
            >
              {{ item.name }}
            </div>
            <div
              class="font-bold tracking-wider text-transparent bg-clip-text bg-gradient-to-r from-[#d37c17] via-[#8f6c44] to-gray-200"
            >
              {{ item.price }} Br
            </div>
          </div>
        </div>
      </template>
    </div>
  </div>
</template>
