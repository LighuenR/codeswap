
<template>
  <div>
    <ULandingCTA
      icon="i-heroicons-rocket-launch"
      title="Trade cryptocurrencies and NFTs with confidence"
      description="Buy, sell and explore tokens and NFTs"
      card
      :links="[
        { label: 'Get started', size: 'lg', to: '/swap' },
        {
          label: 'Learn more',
          variant: 'link',
          color: 'gray',
          size: 'lg',
          trailingIcon: 'i-heroicons-arrow-right-20-solid',
          to: '#aboutUs',
        },
      ]"
    />
    <UCard id="aboutUs">
      <UContainer>
        <ULandingGrid>
        <ULandingCard
          class="col-span-6 row-span-4 bg-swap"
          inactive-class="bg-swap"
          icon="i-heroicons-arrow-path"
          title="Swap Tokens"
          description="Buy, sell, and explore tokens on Ethereum, Polygon, Optimism, and more."
        />
        <ULandingCard
          class="col-span-6 row-span-4"
          icon="i-heroicons-arrows-right-left"
          title="Trade NFTs"
          description="Buy and sell NFTs across marketplaces to find more listings at better prices."
        />
        <ULandingCard
          class="col-span-4 row-span-2"
          icon="i-heroicons-currency-dollar"
          title="Buy crypto"
          description="Buy crypto with your credit card or bank account at the best rates."
        />
        <ULandingCard
          class="col-span-4 row-span-2"
          icon="i-heroicons-arrow-trending-up"
          title="Earn"
          description="Provide liquidity to pools on Uniswap and earn fees on swaps."
        />
        <ULandingCard
          class="col-span-4 row-span-2"
          icon="i-heroicons-plus"
          title="Build Apps"
          description="Build apps and tools on the largest DeFi protocol on Ethereum."
        />
      </ULandingGrid>
      </UContainer>
    </UCard>
  </div>
</template>
 <style>
 .bg-swap {
  background-image: url("/img/bg-swap.png");
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center right;
  opacity: 1;
 }
</style>