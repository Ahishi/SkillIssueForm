<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <nav class="h-[4rem] flex bg-purple-800 text-white">
      <RouterLink class="px-5 py-2.5 block w-fit h-fit my-auto" to="/">Home</RouterLink>
      <RouterLink class="px-5 py-2.5 block w-fit h-fit my-auto" to="/about">About</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>
