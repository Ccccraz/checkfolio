<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";
import { useColorMode } from "@vueuse/core";

var mode = useColorMode({
  disableTransition: false,
});
mode.value = "dark";
</script>

<template>
  <RouterView />
</template>

<style>
body {
  background-color: transparent !important;
}
</style>
