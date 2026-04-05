<script setup>
import { ArrowRight } from '@lucide/vue';
import Button from '../ui/Button.vue';

const services = [
  {
    title: 'Big Data Analytics',
    content:
      'Streamline enterprise analytics with strategic advice on techniques, tools and platforms. Build blueprints to choose the best storage architectures like ODS, data warehouses, data marts.',
  },
  {
    title: 'Big Data Consulting',
    content:
      'Get tailored strategies from our Big Data consulting services that include strategic planning, infrastructure design, data integration, and analytics solutions to improve operational efficiency.',
  },
  {
    title: 'Big Data Implementation',
    content:
      'Extract actionable data, predict customer preferences/market trends with ML, statistical modelling. Build predictive analysis with industry’s best architectures like OLAP cubes.',
  },
  {
    title: 'Data Product Development',
    content:
      'Build accessibility with productized interfaces; manage digital workloads by aligning data patterns into ingestible outputs. Smoothly integrate data products with existing systems. ',
  },
  {
    title: 'Ingest, Storage, Pipeline',
    content:
      'Converge and structure diverse data sources on data lakes. Make data available in useful formats with database model expertise. Manage data pipelines for real-time and historical data.',
  },
  {
    title: 'Generative AI Strategy Consulting',
    content:
      'Recognize the best-fit capabilities for your business with trend analysis in custom Gen AI models. Leverage data engineering and predictive analysis expertise for immersive UX.',
  },
  {
    title: 'Gen AI Business Transformation',
    content:
      'Get wider scope for process transformation with Gen AI Co-pilots to speed up automation and enhance business knowledge. Leverage Gen AI techniques like LLM, Vision and RAG.',
  },
  {
    title: 'Gen AI Product Development',
    content:
      'Invest in a data-led approach for built-to-scale web and mobile-based Gen AI products. Bring accuracy with AI-powered personalization and converge data insights to enhance UX.',
  },
  {
    title: 'Generative AI Integration Services',
    content:
      'Integrate Gen AI into existing workflows for swift decisioning. Use LLM platforms like ChatGTP, Bard, Mistral, Llava to build virtual assistants and bots for better engagement.',
  },
];
</script>

<template>
  <section class="px-8 py-16 lg:px-36 lg:py-20 flex flex-col items-center justify-center gap-8">
    <h2 class="font-semibold text-lg md:text-2xl lg:text-3xl">Support Gen AI Intelligence by Aligning Big Data</h2>

    <div class="grid md:grid-cols-3 gap-6">
      <div v-for="(service, index) in services" :key="index" class="border py-9 px-8 border-[#C3C3C3] rounded-sm">
        <h3 class="font-semibold pb-2">{{ service.title }}</h3>
        <p class="text-sm">{{ service.content }}</p>
      </div>
    </div>

    <Button class="group">
      Grow Data-Led Ecosystems
      <ArrowRight class="inline w-4 h-4 transition-transform group-hover:translate-x-1" />
    </Button>
  </section>
</template>
