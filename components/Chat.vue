<template>
  <section
    class="flex flex-col justify-center antialiased text-gray-600 p-4 max-w-sm absolute bottom-0 right-0 z-10 w-96 "
  >
    <div class="h-full">
      <div class="relative max-w-[340px] mx-auto bg-white shadow-lg rounded-lg h-96">
        <header class="pt-6 pb-4 px-5 border-b border-gray-200">
          <div class="flex justify-between items-center mb-3">
            <!-- Image + name -->
            <div class="flex items-center">
              <a class="inline-flex items-start mr-3" href="#0">
                <img
                  class="rounded-full"
                  src="https://cdn.vuetifyjs.com/images/john.jpg"
                  width="48"
                  height="48"
                  alt="Lauren Marsano"
                />
              </a>
              <div class="pr-1">
                <span
                  class="inline-flex text-gray-800 hover:text-gray-900"
                >
                  <h2 class="text-xl leading-snug font-bold">Oleg Averyanov</h2>
                </span>
              </div>
            </div>
            <!-- Settings button -->
            <div class="relative inline-flex flex-shrink-0">
              <div
                class="text-gray-400 hover:text-gray-500 rounded-full focus:ring-0 outline-none focus:outline-none cursor-pointer"
                v-on:click="$emit('closeMessage')"
              >
                X
              </div>
            </div>
          </div>
        </header>
        <!-- Card body -->
        <div class="py-3 px-5">
          <h3 class="text-xs font-semibold uppercase text-gray-400 mb-1">
            Сообщения
          </h3>
          <!-- Chat list -->
          <div class="divide-y divide-gray-200">
            <!-- User -->
            <div
              v-for="mess in this.messageArr"
              :key="mess.payload.data[0].message.text"
              class="w-full text-left py-2 focus:outline-none focus-visible:bg-indigo-50"
            >
              <div class="flex items-center">
                <img
                  class="rounded-full items-start flex-shrink-0 mr-3"
                  src="https://cdn.vuetifyjs.com/images/john.jpg"
                  width="32"
                  height="32"
                  alt="Marie Zulfikar"
                />
                <div>
                  <h4 class="text-sm font-semibold text-gray-900">
                    {{ mess.payload.data[0].fromUser.name }}
                  </h4>
                  <div class="text-[13px]">{{ mess.payload.data[0].message.text }}</div>
                </div>
              </div>
            </div>
            <!-- User -->
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Shat",
  props: ["messageArr"],
};
</script>

<style scoped></style>
