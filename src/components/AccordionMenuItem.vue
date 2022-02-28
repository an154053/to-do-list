<template>
  <div class="w-80">
    <!-- 下拉式選單 -->
    <label
      :class="[
        'px-4 py-2',
        'border border-gray-300',
        'hover:bg-gray-100',
        'flex items-center justify-between',
        'cursor-pointer',
        'transition-all',
      ]"
    >
      <input type="checkbox" class="sr-only" v-model="checked" />
      <div :class="[checked && 'text-green-500', 'transition-all']">
        {{ itemName }}
      </div>

      <!-- 旁邊的箭頭 -->
      <div
        :class="[
          'h-9 w-9',
          'hover:bg-gray-200',
          'rounded-full',
          'flex items-center justify-center',
          'transition-all',
        ]"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          :class="['h-6 w-6', checked && '-rotate-180', 'transition-all']"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M19 9l-7 7-7-7"
          />
        </svg>
      </div>
    </label>
    <!-- 內容 -->
    <div
      :class="[
        checked ? 'max-h-[300px]' : 'max-h-0',
        'border border-t-0 border-gray-300',
        'overflow-hidden',
        'transition-all',
      ]"
    >
      <slot name="itemContent">
        <div class="p-4 text-gray-600">
          <slot name="itemText"> 內容區 </slot>
        </div>
      </slot>
    </div>
  </div>
</template>
<script>
export default {
  name: "AccordionMenuItem",
  data() {
    return {
      checked: false,
    };
  },

  props: {
    itemName: {
      default: "選項",
    },
  },
};
</script>

<style></style>
