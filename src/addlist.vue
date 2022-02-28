<template>
  <!-- 按鈕 -->
  <div
    :class="[
      'h-screen w-screen',
      'flex flex-col gap-5',
      'juestify-center items-center',
    ]"
  >
    <div class="flex gap-5">
      <input
        :class="[
          'flex-gap-3 flex',
          'px-3 py-3',
          'rounded-md font-bold',
          'border-dark border',
        ]"
      />
      <buttoncleak text="新增" color="blue">
        <template v-slot:iconleft>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M12 6v6m0 0v6m0-6h6m-6 0H6"
            />
          </svg>
        </template>
      </buttoncleak>
    </div>
  </div>
</template>

<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from "./components/HelloWorld.vue";
import buttoncleak from "./components/buttoncleak.vue";
</script>

<style></style>
