<script setup>
import { createWeb3Modal, defaultWagmiConfig } from "@web3modal/wagmi/vue";
import { mainnet, arbitrum, sepolia, goerli } from "viem/chains";

// 1. Get projectId at https://cloud.walletconnect.com
const projectId = "3dc726cfd83b53d24898e4af040d6a69";

// 2. Create wagmiConfig
const metadata = {
  name: "Web3Modal",
  description: "Web3Modal Example",
  url: "https://web3modal.com",
  icons: ["https://avatars.githubusercontent.com/u/37784886"],
};

const chains = [mainnet, arbitrum, sepolia, goerli];
const wagmiConfig = defaultWagmiConfig({ chains, projectId, metadata });

// 3. Create modal
createWeb3Modal({ wagmiConfig, projectId, chains });

const links = [
  {
    label: "Features",
    to: "#features",
    exactHash: true,
  },
  {
    label: "Documentation",
    to: "https://ui.nuxt.com/pro",
    target: "_blank",
  },
];



useSeoMeta({
  description:
    "Nuxt UI Pro is a collection of premium components built on top of Nuxt UI to create beautiful & responsive Nuxt applications in minutes.",
});
</script>

<template>
 
  <TheHeader />
  <UMain>
    <NuxtPage />
  </UMain>

  <TheFooter />
 
</template>
