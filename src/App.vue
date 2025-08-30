<script setup>
import { ref, computed } from "vue";
import Fast from "./components/Fast.vue";
import Yefisk from "./components/Yefisk.vue";
import Beverages from "./components/Beverages.vue";

// Define categories and menu items
const categories = [
  { name: "MAIN COURSE", title: "የፆም ምግቦች" },
  { name: "APPETIZERS", title: "የፍስክ ምግቦች" },
  { name: "BEVERAGES", title: "መጠጦች" },
];

const activeCategory = ref({ name: "APPETIZERS", title: "የፍስክ ምግቦች" });
</script>

<template>
  <div
    class="max-w-[500px] mx-auto p-2 bg-gradient-to-b from-[#090909] via-gray-800 to-[#151514] shadow-xl"
  >
    <!-- Header -->
    <div class="text-center mb-4">
      <!-- Restaurant Name with Gradient -->
      <h1
        class="text-4xl md:text-6xl font-extrabold tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 via-amber-500 to-red-500 drop-shadow-lg animate-gradient-x"
      >
        ታኦስ ቁርጥና<br />
        የባህል ምሽት
      </h1>

      <!-- Contact Info -->
      <p
        class="text-gray-300 text-sm tracking-wider mt-2 flex justify-center items-center gap-3"
      >
        <svg
          class="w-5 h-5 text-amber-600"
          fill="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            d="M2.25 4.5A2.25 2.25 0 014.5 2.25h3a2.25 2.25 0 012.25 2.25v3a2.25 2.25 0 01-2.25 2.25H5.81l1.95 4.29a16.061 16.061 0 006.45 6.45l4.29-1.95v-1.94a2.25 2.25 0 012.25-2.25h3a2.25 2.25 0 012.25 2.25v3a2.25 2.25 0 01-2.25 2.25c-10.493 0-19-8.507-19-19z"
          />
        </svg>

        +251-933-967-236 | ማራኪ መንገድ, ጎንደር
      </p>
    </div>

    <!-- Category Buttons -->
    <div
      class="flex justify-center items-center text-center mb-4 space-x-4 text-xs"
    >
      <div
        v-for="category in categories"
        :key="category.name"
        @click="
          activeCategory = categories.find((cat) => cat.name === category.name)
        "
        :class="[
          'px-5 py-2 rounded-full font-semibold transition-all duration-300 cursor-pointer',
          activeCategory.name === category.name
            ? 'bg-amber-500 text-white shadow-lg '
            : 'bg-gray-700 text-gray-300 hover:bg-amber-500 hover:text-white',
        ]"
      >
        {{ category.title }}
      </div>
    </div>

    <div
      class="text-white text-center tracking-widest text-xl font-bold pb-2 mb-2 text-transparent bg-clip-text bg-gradient-to-r from-gray-200 via-[#ec820a] to-gray-200"
    >
      {{ activeCategory.title }}
    </div>
    <div
      v-if="false"
      class="text-center tracking-widest text-ስም font-bold pb-2 mb-2 bg-gray-200 bg-opacity-100 flex justify-center items-center"
    >
      {{ activeCategory.title }} &times; ስፔሻልስ
    </div>

    <Fast v-if="activeCategory.name === 'MAIN COURSE'" />
    <Yefisk v-if="activeCategory.name === 'APPETIZERS'" />
    <Beverages v-if="activeCategory.name === 'BEVERAGES'" />

    <!-- <hr class="my-3 border" /> -->
    <footer class="text-center text-white tracking-wider my-2">
      ታኦስ &copy; 2025
    </footer>
  </div>
</template>

<style>
body {
  font-family: "Inter", sans-serif;
  background-color: #0f0f0f;
  padding: 0.42rem;
}
.dot-leader {
  display: flex;
  justify-content: space-between;
  position: relative;
}

.dot-leader::after {
  content: "";
  flex: 1;
  border-bottom: 1px dotted #d37c17; /* Dotted line color */
  margin: 0 8px; /* Space between text and dots */
  align-self: center;
}
</style>
