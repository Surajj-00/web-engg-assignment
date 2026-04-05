<script setup>

import { ref } from 'vue';
const activeTab = ref(0);
const setActiveTab = (index) => {
  activeTab.value = index;
};

const tabs = [
  {
    title: 'Secure Digital Core',
    content: 'As a big data solutions provider, we build coming-of-age data foundations and leverage built-to-scale AI architectures that support diverse foundation models. Realign your data ecosystems to handle the disruptions that come with AI integrations. We help you enhance IT infrastructures so that it stays relevant even during model changes.'
  },
  {
    title: 'Smash Analytical Limitations',
    content: 'Overcome the barriers of traditional analytics with AI-powered tools that process massive datasets in real time. We help you unlock deeper insights and make faster, data-driven decisions that keep you ahead of the competition. We help you enhance IT infrastructures, customer support so that it stays relevant even during model changes.'
  },
  {
    title: 'DataOps-led Automation',
    content: 'Streamline your data pipelines with end-to-end automation that reduces manual effort and eliminates bottlenecks. Our DataOps approach ensures continuous data delivery, improved quality, and faster time-to-insight across your organization. We help you enhance IT infrastructures so that it stays relevant even during model changes.'
  },
  {
    title: 'Domain Specific Gen AI',
    content: 'Harness the power of generative AI tailored to your industry unique needs. We build domain specific models that understand your business context, enabling smarter automation, precise recommendations, and scalable intelligent workflows. We help you enhance IT infrastructures so that it stays relevant even during model changes.'
  },
];

</script>

<template>
  <section class="px-8 pt-16 lg:px-36 lg:pt-20">

    <h2 class="heading pb-8 md:pb-8">Helping Build Analytics-AI Convergence :</h2>

    <div class="w-full flex items-center md:justify-start gap-4 md:gap-16 ">

      <!-- Left: tabs -->
      <div class="w-6/12 md:w-5/12 xl:w-3/12 md:pl-8">
        <div v-for="(tab, index) in tabs" :key="index" @click="setActiveTab(index)"
          :class="activeTab === index ? 'border-b-2 border-[#02542D] font-semibold' : 'text-gray-400'"
          class="cursor-pointer py-2 md:py-4 border-b text-xs md:text-sm lg:text-base">
          {{ tab.title }}
        </div>
      </div>

      <!-- Right: content -->
      <div class="w-12/12 md:w-8/12 bg-secondary p-4 md:p-8 text-xs md:text-sm lg:text-base rounded-sm rounded-br-4xl text-pretty">
        {{ tabs[activeTab].content }}
      </div>
    </div>

    <div class="border-b pt-16 md:pt-24 border-[#C3C3C3]"></div>
  </section>
</template>
