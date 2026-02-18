<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue';

const profile = ref({
  name: 'Christopher Contreras',
  slogan: 'Full stack Developer and Teacher',
  avatar: "https://api.dicebear.com/9.x/adventurer/svg?seed=Milo",
  links: [
    {
      id: 1,
      title: 'Github',
      url:'http://github.com/ccontre03',
      icon: 'code',
      description:'Check out my projects',
    },
    {
      id: 2,
      title: 'Linkedin',
      url:'https://linkedin.com/in/christopher-contreras-238a5836b/',
      icon: 'briefcase',
      description:'Connnect with me porfessionally',
    },
    {
      id: 3,
      title: 'Expense Splitter',
      url:'https://expense-splitter-vue.christophercontreras23.workers.dev',
      icon: 'calcProject',
      description:'This is my project from class',
    },
  ],

})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8">
    <!-- Profile Header -->
     <div class="mb-8 flex flex-col items-center text center">
      <div 
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-green-400 shadow-lg shadow-green-500/20 sm:h-32 sm:w-32">
        
        <img 
          :src="profile.avatar" 
          :alt="profile.name"
          class="h-full w-full object-cover"
        />
      </div>
      <h1 class="mb-2 font-display text-2xl font-bold text-white sm:text-3xl">{{ profile.name }}</h1>
      <p class="max-w-xs text-gray-300 sm:text-lg">{{ profile.slogan }}</p>
     </div>

     <!-- Link List-->
      <div class="flex w-full max-w-md flex-col gap-4">
        <LinkCard 
        v-for="link in profile.links" 
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
        />
      </div>

    <!-- Navigate to Info -->
    <RouterLink 
      to="/info" 
      class="mt-8 text-sm text-gray-400 underline-offset-4 hover:underline hover:text-green-400 transition-colors duration-200">
      About me ->
     </RouterLink>
  </main>
</template>
