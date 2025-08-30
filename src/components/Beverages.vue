<script setup>
import { ref, computed } from "vue";
import water from "../assets/water.jpeg";
import leslasa from "../assets/leslasa.jpeg";
import malt from "../assets/malt.jpeg";
import wine from "../assets/wine.jpeg";
import beer from "../assets/beer.jpeg";

const getImage = (index) => {
  return index === 0
    ? leslasa
    : index === 1
    ? water
    : index === 2
    ? malt
    : index === 3
    ? beer
    : wine;
  // return tibs;
};

const beverages = ref([
  {
    name: "ለስላሳ መጠጦች",
    price: 50,
    mini: 1,
    category: "BEVERAGES",
    description: "Creamy milkshake in various flavors",
  },
  {
    name: "ትንሽ ውሃ",
    price: 30,
    mini: 2,
    category: "BEVERAGES",
    description: "Refreshing iced tea with lemon",
  },
  {
    name: "መካከለኛ ውሃ",
    price: 40,
    mini: 2,
    category: "BEVERAGES",
    description: "Freshly squeezed orange juice",
  },
  {
    name: "ትልቅ ውሃ",
    price: 50,
    mini: 2,
    category: "BEVERAGES",
    description: "Hot or iced tea with lemon",
  },
  {
    name: "ንጉስ፣ስንቅ፣ሶፊ",
    price: 75,
    mini: 3,
    category: "BEVERAGES",
    description: "Freshly brewed coffee, regular or decaf",
  },
  {
    name: "ቢራ",
    price: 75,
    mini: 4,
    category: "BEVERAGES",
    description: "Freshly squeezed orange juice",
  },
  {
    name: "ጉደር ትልቁ",
    price: 500,
    mini: 5,
    category: "BEVERAGES",
    description: "Freshly squeezed orange juice",
  },
  {
    name: "አዋሽ",
    price: 550,
    mini: 5,
    category: "BEVERAGES",
    description: "Freshly squeezed orange juice",
  },
  {
    name: "አክሱማዊት፤ ከሚላ",
    price: 800,
    mini: 5,
    category: "BEVERAGES",
    description: "Freshly squeezed orange juice",
  },
  {
    name: "አራዳ",
    price: 90,
    mini: 4,
    category: "BEVERAGES",
    description: "Freshly squeezed orange juice",
  },
  {
    name: "ደብል ጅን",
    price: 70,
    mini: 4,
    category: "BEVERAGES",
    description: "Freshly squeezed orange juice",
  },
  {
    name: "ሲንግል ድራፍት",
    price: 50,
    mini: 4,
    category: "BEVERAGES",
    description: "Freshly squeezed orange juice",
  },
]);

// const filteredItems = computed(() =>
//   menuItems.filter((item) => item.category === activeCategory.value.name)
// );
// const chunkedItems = computed(() => {
//   const chunks = [];
//   for (let i = 0; i < beverages.value.length; i += 5) {
//     chunks.push(beverages.value.slice(i, i + 5));
//   }
//   return chunks;
// });
const chunkedItems = computed(() => {
  const groups = {};
  beverages.value.forEach((item) => {
    if (!groups[item.mini]) {
      groups[item.mini] = [];
    }
    groups[item.mini].push(item);
  });
  return Object.values(groups);
});
</script>

<template>
  <hr class="my-2 border" />

  <div>
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
