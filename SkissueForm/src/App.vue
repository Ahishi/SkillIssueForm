<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <nav class="h-[4rem] flex bg-purple-800 text-white shadow-lg">
      <RouterLink class="px-5 py-2.5 block w-fit h-fit my-auto" to="/">Home</RouterLink>
      <RouterLink class="px-5 py-2.5 block w-fit h-fit my-auto" to="/form">Forms</RouterLink>
      <RouterLink class="px-5 py-2.5 block w-fit h-fit my-auto" to="/">Group</RouterLink>
      <RouterLink class="px-5 py-2.5 block w-fit h-fit my-auto block ml-auto" to="/profile">Profile</RouterLink>
    </nav>
  </header>
  <RouterView />
</template>
