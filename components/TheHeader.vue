<template>
  <div>
    <UHeader :links="links">
      <template #logo>
        Cryptocurrency echange
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
  </div>
</template>

<script setup>
useHead({
  title: "Swap App",
  meta: [{ name: "viewport", content: "width=device-width, initial-scale=1" }],
  link: [{ rel: "icon", href: "/bitcoin.png" }],
  htmlAttrs: {
    lang: "en",
  },
});
const links = [{
  label: 'Home',
  to: '/'
},
{
  label: 'Swap',
  icon: 'i-simple-icons-github',
  to: '/swap'
},
{
  label: "Send",
  to: "/send"
}
]

</script>

