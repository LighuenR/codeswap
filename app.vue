<script setup>
import { createWeb3Modal, defaultWagmiConfig } from "@web3modal/wagmi/vue";
import { mainnet, arbitrum } from "viem/chains";

// 1. Get projectId at https://cloud.walletconnect.com
const projectId = "YOUR_PROJECT_ID";

// 2. Create wagmiConfig
const metadata = {
  name: "Web3Modal",
  description: "Web3Modal Example",
  url: "https://web3modal.com",
  icons: ["https://avatars.githubusercontent.com/u/37784886"],
};

const chains = [mainnet, arbitrum];
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

useHead({
  title: "Nuxt UI Pro - Starter",
  meta: [{ name: "viewport", content: "width=device-width, initial-scale=1" }],
  link: [{ rel: "icon", href: "/favicon.ico" }],
  htmlAttrs: {
    lang: "en",
  },
});

useSeoMeta({
  description:
    "Nuxt UI Pro is a collection of premium components built on top of Nuxt UI to create beautiful & responsive Nuxt applications in minutes.",
});
</script>

<template>
  <UHeader :links="links">
    <template #logo>
      Nuxt UI Pro <UBadge label="Starter" variant="subtle" class="mb-0.5" />
    </template>

    <template #right>
      <UColorModeButton />
      <w3m-button />

      <UButton
        to="https://github.com/nuxt-ui-pro/starter"
        target="_blank"
        icon="i-simple-icons-github"
        aria-label="GitHub"
        color="gray"
        variant="ghost"
      />
    </template>
  </UHeader>

  <UMain>
    <NuxtPage />
  </UMain>

  <UFooter>
    <template #left> Copyright © {{ new Date().getFullYear() }} </template>
  </UFooter>
</template>
