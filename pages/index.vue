<template>
  <div>
      <div class="container w-full flex items-center justify-center  p-2">
          <div class="w-full h-full p-2 flex  flex-wrap gap-5 items-center justify-center ">
              <div v-for="data in details" :key="data.id" class="flex flex-col gap-2 bg-white shadow-lg rounded-xl p-2 md:p-3 white:bg-neutral-900 dark:border-neutral-700 dark:text-neutral-400">
                  <div class="top-box w-96 h-10   flex justify-between">
                      <span class="text-gray-400 font-medium text-gray-500">#{{ data.id }}</span>
                      <div class="open-box w-24   flex justify-end items-center justify-between">
                        
                        
                          <button type="button" class="p-1 inline-flex items-center gap-x-2 text-sm font-semibold  border border-transparent bg-yellow-400 text-black hover:bg-white disabled:opacity-50 disabled:pointer-events-none">
                              Open
                          </button>
                          <i class="fa-solid fa-circle-check p-2 text-green-500 text-xl"></i>
                      </div>
                  </div>
                  <div class="title w-96   p-2">
                      
                      <h3 class="text-black text-lg font-semibold">{{ data.title }}</h3>
                      <p class="text-black flex gap-2"><span>{{ data.date }}</span><span>{{ data.time }}</span></p>
                  </div>
                  <div class="para w-96 h-10   p-2 bg-gray-100 rounded-md truncate">
                      <p class="text-black">{{ data.message }}</p>
                  </div>
              </div>
          </div>
      </div>
    
  </div>
</template>

<script setup>
const{data: details}=await useFetch('https://g1.gwcindia.in/ticket-api/g-data.json')
</script>

<style scoped>

</style>