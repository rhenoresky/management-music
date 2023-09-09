<script setup>
defineProps({
  task: Object
})
</script>

<template>
  <div class="flex gap-4 rounded-md bg-[#A6B1E1] shadow p-4 items-center mb-2 mr-1">
    <div class="flex items-center">
      <input type="checkbox" :checked="task.isDone">
    </div>
    <div class="flex flex-col gap-1">
      <p class="text-xl font-semibold text-[#F4EEFF]">
        {{ task.title }}
      </p>
      <p class="text-xl font-semibold text-[#DCD6F7]">
        {{ task.description }}
      </p>
      <p class="text-xl font-semibold text-[#DCD6F7]">
        #{{ task.category }}
      </p>
    </div>
  </div>
</template>

<style scoped>
input[type="checkbox"] {
  appearance: none;
  -webkit-appearance: none;
  width: 20px;
  height: 20px;
  cursor: pointer;
  border: 2px solid #DCD6F7;
  border-radius: 4px;
  display: flex;
  justify-content: center;
  align-items: center;
}

input[type="checkbox"]::after {
  content: "\2713";
  color: #F4EEFF;
  font-weight: 900;
  display: none;
}

input[type="checkbox"]:hover {
  background-color: #dcd6f786;
}

input[type="checkbox"]:checked::after {
  display: block;
}
</style>