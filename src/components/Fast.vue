<script setup>
import { ref, computed } from "vue";
import shiro from "../assets/shiro.jpeg";
import aynet from "../assets/aynet.jpeg";
import pasta from "../assets/pasta.jpeg";

const getImage = (index) => {
  return index === 0 ? shiro : index === 1 ? pasta : aynet;
};

const isSpecial = ref(false);

const fast = ref([
  {
    name: "ሽሮ በድስት",
    price: 160,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ሽሮ በአትክልት",
    price: 143,
    mini: 1,

    category: "MAIN COURSE",
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ሽሮ ላላ",
    mini: 1,
    price: 143,
    category: "MAIN COURSE",
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ሽሮ ተጋቢኖ",
    mini: 1,
    price: 143,
    category: "MAIN COURSE",
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ሽሮ በቲማቲም",
    mini: 1,
    price: 160,
    category: "MAIN COURSE",
    description: "Toasted bread with a blend of melted cheeses",
  },
  {
    name: "ሽሮ በተልባ",
    mini: 1,
    price: 180,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ሽሮ በአትክልት በተልባ",
    mini: 1,
    price: 180,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "የፆም ፍርፍር",
    mini: 2,
    price: 140,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ፓስታ በእንጀራ",
    mini: 2,
    price: 170,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ተልባ ወጥ",
    mini: 3,
    price: 160,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ፓስታ በዳቦ",
    mini: 2,
    price: 160,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "አትክልት በዳቦ",
    mini: 2,
    price: 160,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ፓስታ በአትክልት በእንጀራ",
    mini: 2,
    price: 175,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "የበሰለ አትክልት",
    mini: 2,
    price: 170,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "የበሰለ አትክልት በዳቦ",
    mini: 2,
    price: 155,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ሱፍ ፍትፍት",
    mini: 2,
    price: 160,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ተልባ ፍትፍት",
    price: 170,
    mini: 3,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ጎመን በተልባ",
    mini: 2,
    price: 160,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ጎመን ክትፎ",
    mini: 2,
    price: 150,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ሽርሽም በተልባ",
    mini: 3,
    price: 170,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ሽርሽም ወጥ",
    price: 170,
    mini: 3,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "በየአይነት",
    mini: 3,
    price: 180,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ምስር በድስት",
    mini: 3,
    price: 180,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ክክ በድስት",
    mini: 3,
    price: 180,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ስፔሻል አትክልት ሳላድ",
    mini: 2,
    price: 210,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ቲማቲም ለብለብ",
    mini: 2,
    price: 140,
    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "አትክልት ሳላድ",
    price: 140,
    mini: 2,

    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ቲማቲም ቁርጥ በእንጀራ",
    price: 170,
    mini: 2,

    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ዳቦ ፍርፍር",
    price: 130,
    mini: 3,

    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ድንች ወጥ በተልባ",
    price: 180,
    mini: 3,

    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ስፔሻል ድንች ፍርፍር",
    price: 210,
    mini: 3,

    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ኖርማል ድንች ፍርፍር",
    price: 160,
    mini: 3,

    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ስፔሻል ድንች  ጥብስ",
    price: 260,
    mini: 3,

    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
  {
    name: "ሀፍ ሀፍ",
    price: 360,
    mini: 3,

    category: "MAIN COURSE",
    description: "Crispy chicken breast with fresh toppings",
  },
]);

const specials = ref([
  {
    name: "ማህበራዊ",
    price: 650,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ባህላዊ",
    price: 400,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ታኦስ ስፔሻል",
    price: 600,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ማዕድ ስፔሻል",
    price: 350,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ስፔሻል የፆም ፍርፍር",
    price: 250,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ሙሉ አገልግል",
    price: 380,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ግማሽ አገልግል",
    price: 310,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ትኑር ጎንደር",
    price: 530,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ስፔሻል ዳቦ ፍርፍር",
    price: 250,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ስጋ ለምኔ",
    price: 400,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ዋው ስፔሻል",
    price: 350,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ስፔሻል ምስር ፍርፍር",
    price: 250,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ልዩ ስፔሻል",
    price: 550,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
  {
    name: "ተፈርሾ",
    price: 350,
    category: "MAIN COURSE",
    mini: 1,
    description: "Juicy beef patty with melted cheese on a toasted bun",
  },
]);

// const filteredItems = computed(() =>
//   menuItems.filter((item) => item.category === activeCategory.value.name)
// );
const chunkedItems = computed(() => {
  const groups = {};
  fast.value.forEach((item) => {
    if (!groups[item.mini]) {
      groups[item.mini] = [];
    }
    groups[item.mini].push(item);
  });
  return Object.values(groups);
});
</script>

<template>
  <!-- <div
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
  </div> -->

  <hr class="my-2 border" />
  <div class="text-center text-lg tracking-widest text-white mb-1">
    ታኦስ የፆም ስፔሻልስ
  </div>
  <div
    class="grid grid-cols-2 gap-x-6 gap-y-4 w-full max-w-3xl mx-auto border-2 border-orange-400 rounded-md p-2"
  >
    <div
      v-for="(item, index) in specials"
      :key="item.name"
      class="flex justify-between items-center px-3 py-2 rounded-xl shadow-sm transition transform hover:scale-105 hover:shadow-md text-xs"
      :class="
        index % 2 === 0
          ? 'bg-gradient-to-r from-gray-400 via-[#aaa]/20 to-[#fcfcfc]/20'
          : 'bg-gradient-to-r from-[#fcfcfc]/20 via-[#aaa]/20 to-gray-400'
      "
    >
      <!-- Name -->
      <span
        class="font-bold text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 via-yellow-300 to-yellow-500"
      >
        {{ item.name }}
      </span>
      <!-- Price -->
      <span
        class="font-bold text-transparent bg-clip-text bg-gradient-to-r from-yellow-500 via-yellow-300 to-yellow-400"
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
              class="font-bold tracking-wider text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 via-yellow-300 to-yellow-500"
            >
              {{ item.name }}
            </div>
            <div
              class="font-bold tracking-wider text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 via-yellow-300 to-yellow-500"
            >
              {{ item.price }} Br
            </div>
          </div>
        </div>
        <div
          class="w-[45%] aspect-square rounded-tl-full rounded-bl-full bg-[#F78400] flex justify-center items-center"
        >
          <div
            class="w-[95%] aspect-square bg-[#322c2c] rounded-full flex justify-center items-center"
          >
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
              class="font-bold tracking-wider text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 via-yellow-300 to-yellow-500"
            >
              {{ item.name }}
            </div>
            <div
              class="font-bold tracking-wider text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 via-yellow-300 to-yellow-500"
            >
              {{ item.price }} Br
            </div>
          </div>
        </div>
      </template>
    </div>
  </div>
</template>
