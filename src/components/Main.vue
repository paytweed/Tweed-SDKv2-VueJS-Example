<script setup lang="ts">
import { useAuth, useWeb3, Network } from '@paytweed/core-vue'
import { BrowserProvider } from 'ethers'

const { connect } = useAuth()
const { getEthereumProvider } = useWeb3()

function connnectToTweed ()  {
  connect({ oauth: false }).then((key: any) => {
    console.log({key})
  })
}

async function sendTransaction () {
  const provider = await  getEthereumProvider(Network.ETHEREUM_SEPOLIA)
  const browserProvider = new BrowserProvider(provider)
  const signer = await browserProvider.getSigner()
  const tx = await signer.sendTransaction({
    to: "0x7f8e0B31dd7e8C12cF907225E25Ed83C649bCc62",
    value: 0
  })
  console.log({tx})

}

</script>

<template>
  <div>
    <h1>Vue Example</h1>
    <button @click="connnectToTweed">Connect to Tweed</button>
    <button @click="sendTransaction">send transaction</button>
  </div>
</template>
