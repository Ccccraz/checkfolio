<script setup lang="ts">
import { open } from "@tauri-apps/plugin-dialog";
import Button from "@/components/ui/button/Button.vue";
import {
  Card,
  CardTitle,
  CardHeader,
  CardContent,
  CardDescription,
} from "@/components/ui/card";

async function picker() {
  const file = await open({
    multiple: false,
    directory: true,
  });

  if (file) {
    console.log("Selected directory:", file);
  }
}
</script>

<template>
  <div class="flex items-center justify-center min-h-screen">
    <Card class="min-w-xs w-[40%] bg-card/60">
      <CardHeader>
        <CardTitle>Create event</CardTitle>
        <CardDescription
          class="text-base/relaxed text-muted-foreground tracking-wide"
          >Start from creating a new event: For example, if you are preparing
          documents for visa application this time, then create a folder named
          <span class="font-medium text-foreground">"visa"</span
          >.</CardDescription
        >
      </CardHeader>
      <CardContent class="flex justify-center">
        <Button @click="picker" class="w-full">Start</Button>
      </CardContent>
    </Card>
  </div>
</template>
