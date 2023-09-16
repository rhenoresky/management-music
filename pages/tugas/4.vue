<script setup>
const listTask = reactive([
  {
    title: 'Title 1',
    description: 'Ini Deskripsi',
    isDone: false,
    category: 'Olahraga'
  },
  {
    title: 'Title 2',
    description: 'Ini Deskripsi',
    isDone: false,
    category: 'Bekerja'
  },
  {
    title: 'Title 3',
    description: 'Ini Deskripsi',
    isDone: false,
    category: 'Belajar'
  },
  {
    title: 'Title 4',
    description: 'Ini Deskripsi',
    isDone: false,
    category: 'Olahraga'
  },
  {
    title: 'Title 5',
    description: 'Ini Deskripsi',
    isDone: false,
    category: 'Belajar'
  },
])

const tasks = computed(() => {
  if (!filterValue.value) {
    return listTask
  }
  if (filterValue.value === 'Olahraga') {
    let newTask = []
    listTask.map((task) => {
      if (task.category === 'Olahraga') {
        newTask.push(task)
      }
    })
    return newTask
  }
  if (filterValue.value === 'Belajar') {
    let newTask = []
    listTask.map((task) => {
      if (task.category === 'Belajar') {
        newTask.push(task)
      }
    })
    return newTask
  }
  if (filterValue.value === 'Bekerja') {
    let newTask = []
    listTask.map((task) => {
      if (task.category === 'Bekerja') {
        newTask.push(task)
      }
    })
    return newTask
  }
})

const isCreating = ref(false)
const title = ref('')
const description = ref('')
const category = ref('')
const filterValue = ref('')

function addTask() {
  listTask.push({
    title: title.value,
    description: description.value,
    isDone: false,
    category: category.value
  })
  title.value = ''
  description.value = ''
  category.value = ''
}

</script>

<template>
  <section class="w-full bg-[#424874] min-h-screen flex justify-center">
    <div class="w-[80%]">
      <h1 class="text-6xl text-center text-[#A6B1E1] font-bold mb-4 drop-shadow">
        List Task
      </h1>
      <div class="w-full h-[390px] flex justify-center gap-4">
        <div class="h-full w-[55%]">
          <div class="flex justify-between">
            <select v-model="filterValue"
              class="bg-[#A6B1E1] cursor-pointer outline-none text-[#DCD6F7] rounded py-1 px-2 mb-2 items-end">
              <option value="" disabled hidden>Filter</option>
              <option value="">Semua</option>
              <option value="Olahraga">Olahraga</option>
              <option value="Belajar">Belajar</option>
              <option value="Bekerja">Bekerja</option>
            </select>
            <div>
              <button v-if="!isCreating" @click="isCreating = !isCreating"
                class="bg-[#A6B1E1] hover:bg-opacity-[85%] px-2 py-1 rounded text-[#DCD6F7]">
                Add Task
              </button>
            </div>
          </div>
          <div class="h-full overflow-y-auto">
            <CardItem v-for="(task, i) of tasks" :task="task" :key="i" />
          </div>
        </div>
        <form @submit.prevent="addTask" v-if="isCreating" class="flex flex-col w-[40%] gap-2 mt-[38px]">
          <input v-model="title" type="text"
            class="h-8 w-full rounded bg-[#A6B1E1] px-2 placeholder:text-[#DCD6F7] text-[#F4EEFF] outline-none focus:ring-1 focus:ring-inset focus:ring-[#F4EEFF]"
            placeholder="Title">
          <textarea v-model="description" rows="6"
            class="w-full rounded bg-[#A6B1E1] px-2 placeholder:text-[#DCD6F7] text-[#F4EEFF] outline-none py-1 focus:ring-1 focus:ring-inset focus:ring-[#F4EEFF]"
            placeholder="Description">
          </textarea>
          <select v-model="category" class="bg-[#A6B1E1] outline-none text-[#DCD6F7] rounded py-1 px-2">
            <option value="" disabled hidden>Pilih Kategori</option>
            <option value="Olahraga">Olahraga</option>
            <option value="Belajar">Belajar</option>
            <option value="Bekerja">Bekerja</option>
          </select>
          <div class="flex gap-2 mt-2">
            <button type="submit"
              class="bg-[#A6B1E1] px-2 py-1 rounded text-[#F4EEFF] hover:bg-opacity-[85%]">Save</button>
            <button @click="isCreating = !isCreating"
              class="bg-[#A6B1E1] px-2 py-1 rounded text-[#F4EEFF] hover:bg-opacity-[85%]">Cancel</button>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<style scoped>
::-webkit-scrollbar {
  width: 12px;
}

::-webkit-scrollbar-track {
  background: #424874;
}

::-webkit-scrollbar-thumb {
  background: #DCD6F7;
  border-radius: 10px;
}
</style>