<template>
  <!-- 
    mobile                desktop
    ============          =  =    =             =
    ============          =  =    =             =
                          =  =    =             =
                          =  =    =             =
    ============          =  =    =             =
    ============          =  =    =             =
   -->
  <div class="h-screen flex flex-col overflow-hidden">
    <!-- top section -->
    <div class="flex-shrink-0 xl:hidden h-1/6 overflow-hidden wireframe">
      <!-- start content slot -->
      <!-- add overflow-x-auto for scroll -->
      <div class="h-full flex items-center space-x-4 overflow-x-auto">
        <div
          v-for="a in 100"
          :key="a"
          class="text-center text-8xl font-black text-gray-100"
        >
          {{ a }}
        </div>
      </div>
      <!-- end content slot -->
    </div>

    <!-- middle section -->
    <div class="flex-1 flex overflow-hidden">
      <!-- add sidebars for large screens -->
      <div class="flex-shrink-0 hidden xl:flex overflow-hidden">
        <!-- add overflow-y-auto for scrollable content on child elements -->
        <div class="w-20 wireframe"></div>
        <div class="w-64 overflow-y-auto wireframe">
          <div
            v-for="b in 100"
            :key="b"
            class="text-center text-8xl font-black text-gray-100"
          >
            {{ b }}
          </div>
        </div>
      </div>

      <!-- main -->
      <div class="flex-1 flex flex-col overflow-hidden">
        <!-- start content slot -->
        <!-- add overflow-y-auto to child for scroll -->
        <div class="h-full wireframe overflow-y-auto">
          <!-- <Nuxt /> -->
          <div
            v-for="c in 100"
            :key="c"
            class="text-center text-8xl font-black text-gray-100"
          >
            {{ c }}
          </div>
        </div>
        <!-- end content slot -->
      </div>
    </div>

    <!-- bottom -->
    <div class="xl:hidden flex-shrink-0 h-1/6 wireframe">
      <!-- start content slot -->
      <!-- add overflow-x-auto for scroll -->
      <div class="h-full flex items-center space-x-4 overflow-x-auto">
        <div
          v-for="a in 100"
          :key="a"
          class="text-center text-8xl font-black text-gray-100"
        >
          {{ a }}
        </div>
      </div>
      <!-- end content slot -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppLayout',
}
</script>

<style lang="postcss">
.wireframe {
  @apply m-2 border-2 border-dashed border-gray-400;
}
</style>
