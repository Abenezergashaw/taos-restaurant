<script setup>
import { ref } from "vue";

const catagories = ref([
  {
    catagory: "የፆም ምግቦች",
    catagories: {
      special: [
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
      ],
      normal: [
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
        {
          name: "ሽሮ በድስት",
          price: "160",
        },
      ],
    },
  },
  {
    catagory: "የፍስክ ምግቦች",
    lists: [
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
    ],
  },
  {
    catagory: "መጠጦች",
    lists: [
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
      {
        name: "ሽሮ በድስት",
        price: "160",
      },
    ],
  },
]);
</script>

<template>
  <div
    class="w-full max-w-[768px] h-screen mx-auto px-4 sm:px-6 lg:px-8 pt-2 bg-gradient-to-b from-[#090909] to-[#252423]"
  >
    <h2
      class="text-center text-white font-asimovian font-bold text-4xl tracking-widest mb-2"
    >
      FOOD MENU
    </h2>
    <div
      class="text-center text-white font-asimovian font-bold text-2xl tracking-widest mb-2 border-b-2 pb-2"
    >
      ታኦስ ሬስቶራንት
    </div>

    <div class="text-white flex justify-center items-center gap-4">
      <div
        class="bg-[#F78400] text-black rounded-lg px-4 py-2 text-xl tracking-widest shadow-lg shadow-[#777]"
      >
        የፆም ምግቦች
      </div>
      <div class="rounded-lg px-4 py-2 text-xl tracking-widest">የፍስክ ምግቦች</div>
    </div>
  </div>
</template>
