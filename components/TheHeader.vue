<template>
  <div>
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
  </div>
</template>

<script setup>
useHead({
  title: "Nuxt UI Pro - Starter",
  meta: [{ name: "viewport", content: "width=device-width, initial-scale=1" }],
  link: [{ rel: "icon", href: "/favicon.ico" }],
  htmlAttrs: {
    lang: "en",
  },
});
</script>

