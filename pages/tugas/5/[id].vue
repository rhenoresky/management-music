<script setup>
const {id} = useRoute().params
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
    <h1 class="text-4xl font-semibold text-[#FEFFDE] text-center">Detail Article</h1>
  </header>
  <main class="w-full flex justify-center items-center flex-col py-8 gap-4 text-[#FEFFDE]">
    <section class="w-4/5 bg-[#91C788] flex justify-center rounded overflow-hidden p-4 shadow gap-4">
      <div class="basis-1/2 rounded-md overflow-hidden shadow">
        <img :src="articles[id].img" alt="gambar-article" class="w-full h-full object-cover object-center">
      </div>
      <div class="basis-1/2">
        <h1 class="text-xl font-medium mb-4">{{ articles[id].title }}</h1>
        <p class="text-justify text-sm">{{ articles[id].content }}</p>
      </div>
    </section>
    <NuxtLink to="/tugas/5/" class="px-4 py-2 bg-[#91C788] rounded text-[#FEFFDE] my-2">Kembali</NuxtLink>
  </main>
</template>