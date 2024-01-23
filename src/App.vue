<script setup lang="ts">
import { TweedProvider } from "@paytweed/core-vue";
import Main from './components/Main.vue';


const clientOptions = {
  // baseUrl: "https://api-core.local.paytweed.com",
  chains: [1]
}

</script>

<template>
  <TweedProvider applicationId="f0f3e353-fb13-4b2f-a362-2a9fc7d29ad4"  :options="clientOptions" >
    <Main  />
  </TweedProvider>
</template>

