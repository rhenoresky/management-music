<script setup>
const articles = reactive([
  {
    title: "Judul Artikel 1",
    content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat dolor explicabo sint quos exercitationem fugiat reiciendis assumenda. Ad quia veritatis, dolor odit, voluptas numquam modi porro eius reprehenderit ullam tenetur?",
    img: 'https://images.unsplash.com/photo-1649282806617-c51bb282899c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80'
  },
  {
    title: "Judul Artikel 2",
    content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat dolor explicabo sint quos exercitationem fugiat reiciendis assumenda. Ad quia veritatis, dolor odit, voluptas numquam modi porro eius reprehenderit ullam tenetur?",
    img: 'https://images.unsplash.com/photo-1635732646038-0a1a2fe3f2d6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1074&q=80'
  },
  {
    title: "Judul Artikel 3",
    content: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat dolor explicabo sint quos exercitationem fugiat reiciendis assumenda. Ad quia veritatis, dolor odit, voluptas numquam modi porro eius reprehenderit ullam tenetur?",
    img: 'https://images.unsplash.com/photo-1640006807976-a6127e9d6fa0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1171&q=80'
  },
])
</script>

<template>
  <header class="w-full bg-[#91C788] py-4">
    <h1 class="text-4xl font-semibold text-[#FEFFDE] text-center">List Article</h1>
  </header>
  <main class="w-full flex justify-center items-center flex-wrap py-8 gap-4 text-[#FEFFDE]">
    <section v-for="(article, i) of articles" :key="i"
      class="w-1/5 bg-[#91C788] flex justify-center items-center flex-col rounded overflow-hidden p-2 shadow gap-2">
      <div class="w-full h-32 rounded-md overflow-hidden shadow">
        <img :src="article.img" alt="gambar-article" class="w-full h-full object-cover object-center">
      </div>
      <h1 class="text-xl font-medium mt-2">{{ article.title }}</h1>
      <p class="line-clamp-4 text-justify text-sm">{{ article.content }}</p>
      <NuxtLink :to="'/tugas/5/' + i" class="px-4 py-2 bg-[#DDFFBC] rounded text-[#91C788] my-2">Detail</NuxtLink>
    </section>
  </main>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Amatic+SC:wght@700&family=Montserrat:wght@100;200;300;400;500;600;700;800;900&display=swap');

body {
  background-color: #52734D;
  font-family: 'Montserrat', sans-serif;
}
</style>