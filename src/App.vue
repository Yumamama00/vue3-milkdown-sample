<template>
  <main>
    <div style="margin-right: auto; margin-left: auto; width: 80%">
      <h1>Vue3 + Milkdown Sample</h1>

      <MilkdownEditor v-model="content" />
    </div>
  </main>
</template>

<script setup lang="ts">
import { ref } from "vue";
import MilkdownEditor from "./components/MilkdownEditor.vue";

const content = ref<string>("Vue3 + Milkdown");
</script>

<style>
@import "@/assets/font.css";
@import "@/assets/mdi.css";
</style>
