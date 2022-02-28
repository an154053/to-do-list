<template>
  <div
    :class="[
      'h-screen w-screen',
      'flex flex-col gap-5',
      'juestify-center items-center',
    ]"
  >
    <div class="flex gap-5">
      <!-- 搜尋 -->
      <input
        :class="[
          'flex-gap-3 flex',
          'px-3 py-3',
          'rounded-md font-bold',
          'border-dark border',
        ]"
      />
      <!-- 新增按鈕 -->
      <buttoncleak text="新增行程" color="blue">
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
    <!-- 顯示行程 -->

    <AccordionMenuItem
      v-for="item in list.items"
      :key="list.groupName.concat('-', item.name)"
      :itemName="item.name"
    >
      <template v-slot:itenText> {{ item.content }} </template>
    </AccordionMenuItem>
  </div>
</template>

<script>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from "./components/HelloWorld.vue";
import buttoncleak from "./components/buttoncleak.vue";
import AccordionMenuItem from "./components/AccordionMenuItem.vue";

export default {
  data() {
    return {
      list: {
        groupName: "Abouts",
        items: [
          {
            name: "關於兔兔教",
            content:
              "不是邪教，但不太正常 (？)。 不過可以為你在此獻上教義 ... (住嘴！)",
          },
          {
            name: "關於 Tailwind CSS",
            content: "超讚了啦，不用真是太可惜了！",
          },
          { name: "關於手風琴", content: "流浪到淡水時有機會可以看到。" },
          { name: "關於兔兔", content: "你想知道的太多了，去擲筊問神吧！！！" },
        ],
      },
      faq: {
        groupName: "FAQ",
        links: [
          { name: "四大超商", contents: ["7-11", "全家", "萊爾富", "OK"] },
          {
            name: "付款方式",
            contents: ["現金", "ATM", "信用卡", "LINE PAY", "五倍券"],
          },
          { name: "取貨方式", contents: ["宅配", "超商取貨"] },
        ],
      },
    };
  },
};
</script>

<style></style>
