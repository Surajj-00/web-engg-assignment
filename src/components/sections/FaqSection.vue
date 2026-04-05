<script setup>
const faqs = [
  {
    question: 'What do your Generative AI development services include?',
    answer: 'Our Generative AI development services include model training, fine-tuning, prompt engineering, and deployment of AI solutions tailored to your business needs.'
  },
  {
    question: 'What industries benefit the most from Big Data and Generative AI solutions?',
    answer: 'Industries like healthcare, finance, retail, manufacturing, and logistics benefit greatly from Big Data and Generative AI through improved decision-making and automation.'
  },
  {
    question: 'How do Big Data and Gen AI work together to drive business insights?',
    answer: 'Big Data provides the foundation of large-scale data collection and processing, while Gen AI extracts meaningful patterns and generates actionable insights from that data.'
  },
  {
    question: 'How do Big Data and Generative AI impact data privacy?',
    answer: 'We follow strict data governance frameworks and compliance standards to ensure all data processing and AI operations respect user privacy and regulatory requirements.'
  },
  {
    question: 'How do Big Data and Generative AI improve operational efficiency in enterprises?',
    answer: 'By automating repetitive tasks, optimizing workflows, and providing real-time analytics, Big Data and Gen AI significantly reduce operational costs and improve productivity.'
  },
  {
    question: 'What are the best tools and platforms for Gen AI and Big Data?',
    answer: 'Popular tools include Apache Spark, Hadoop, TensorFlow, PyTorch, LangChain, and cloud platforms like AWS, Google Cloud, and Azure for scalable AI and data solutions.'
  },
];

import { Minus, Plus } from '@lucide/vue';
import { ref } from 'vue';
const activeIndex = ref(null);

const toggleFaq = (index) => {
  activeIndex.value = activeIndex.value === index ? null : index;
}

</script>

<template>
  <section class="px-8 py-16 lg:px-36 lg:py-20">

    <div class="md:grid grid-cols-3 gap-12">

      <!-- Left: heading (takes 1 col) -->
      <div>
        <h2 class="font-semibold text-lg md:text-2xl lg:text-3xl pb-8 text-center md:text-start">Frequently Asked Questions</h2>
      </div>

      <!-- Right: faq list (takes 2 cols) -->
      <div class="col-span-2 flex flex-col gap-4">
        <div v-for="(faq, index) in faqs" :key="index" class="border border-[#D3D3D3] rounded-md p-4 cursor-pointer select-none"
          @click="toggleFaq(index)">
          <!-- question row -->
          <div class="flex justify-between items-center">
            <span class="font-semibold text-sm md:text-base">{{ faq.question }}</span>
            <!-- <span>{{ activeIndex === index ? '−' : '+' }}</span> -->
            <Plus v-if="activeIndex !== index" class="w-4 h-4 shrink-0" />
            <Minus v-if="activeIndex === index" class="w-4 h-4 shrink-0" />
          </div>

          <!-- answer — only when active -->
          <p v-show="activeIndex === index" class="mt-3 text-gray-500 text-xs md:text-sm">
            {{ faq.answer }}
          </p>
        </div>
      </div>

    </div>

  </section>
</template>
