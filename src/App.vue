<script setup lang="ts">
import { Network, TweedProvider } from "@paytweed/core-vue";
import Main from './components/Main.vue';

const clientOptions = {
  chains: [Network.ETHEREUM],
};

</script>

<template>
  <TweedProvider applicationId="YOUR-APP-ID"  :options="clientOptions" >
    <Main />
  </TweedProvider>
</template>

