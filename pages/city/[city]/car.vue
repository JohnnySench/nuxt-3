<script setup lang="ts">
const route = useRoute()
const toTitleCase = (str: string): string => {
  return str.replace(/\w\s*/g, function (txt: string) {
    return txt.charAt(0).toUpperCase() + txt.substring(1).toLowerCase()
  })
}
useHead({
  title: `${route.params.make ? toTitleCase(route.params.make as string) :
                  'Cars'} in ${toTitleCase(route.params.city as string)}`
})
</script>

<template>
  <NavBar />
  <div class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-3/5">
    <div class="mt-32 flex">
      <CarSideBar />
      <NuxtPage />
    </div>
  </div>
</template>

<style scoped>

</style>