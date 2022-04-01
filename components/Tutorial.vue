
<template>
  <div>
    <button @click="connect">connect</button>
  </div>
</template>

<script>
import Onboard from '@web3-onboard/core'
import injectedModule from '@web3-onboard/injected-wallets'

const onboard = Onboard({
    wallets: [
      injectedModule()
    ],
    chains: [
      {
        id: '0x1',
        token: 'ETH',
        label: 'Ethereum Mainnet',
        rpcUrl: 'https://mainnet.infura.io/v3/eb347fc6f4b84938bf8b111cc08a4814'
      },
      {
        id: '0x3',
        token: 'tROP',
        label: 'Ethereum Ropsten Testnet',
        rpcUrl: 'https://ropsten.infura.io/v3/eb347fc6f4b84938bf8b111cc08a4814'
      },
      {
        id: '0x4',
        token: 'rETH',
        label: 'Ethereum Rinkeby Testnet',
        rpcUrl: 'https://rinkeby.infura.io/v3/eb347fc6f4b84938bf8b111cc08a4814'
      },
      {
        id: '0x89',
        token: 'MATIC',
        label: 'Matic Mainnet',
        rpcUrl: 'https://matic-mainnet.chainstacklabs.com'
      }
    ]
  })

export default {
  name: 'NuxtTutorial',
  methods: {
    connect() {
      onboard.connectWallet()
    }
  }
}
</script>
