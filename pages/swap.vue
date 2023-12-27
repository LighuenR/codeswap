<script setup>
const items = [
  [
    {
      label: "Profile",
      avatar: {
        src: "https://avatars.githubusercontent.com/u/739984?v=4",
      },
    },
  ],
];
</script>

<template>
  <UContainer class="flex flex-col gap-4 form-size mt-8">
    <UForm>
      <UCard>
        <template #header>
          <div class="grid grid-cols-2">
            <div class="grid grid-cols-4 ml-4">
              <h1>Swap</h1>
              <h1>Buy</h1>
            </div>
            <div class="grid grid-cols-1 justify-items-end">
              <UButton
                icon="i-heroicons-cog-8-tooth"
                size="sm"
                color="primary"
              />
            </div>
          </div>
        </template>

        <div class="grid grid-cols-2 gap-1">
          <UInput
            class="w-full"
            icon="i-heroicons-magnifying-glass-20-solid"
            size="sm"
            color="white"
            :trailing="false"
            placeholder="You will pay"
            :padder="false"
            variant="none"
          />
          <UDropdown :items="items" :popper="{ placement: 'right-start' }">
            <UButton
              color="white"
              label="Options"
              trailing-icon="i-heroicons-chevron-down-20-solid"
              class="w-full"
              variant="ghost"


      
            />
          </UDropdown>
        </div>

        <UDivider icon="i-heroicons-arrow-long-down" class="my-2" />

        <div class="grid grid-cols-2 gap-1">
          <UInput
            class="w-full"
            icon="i-heroicons-magnifying-glass-20-solid"
            size="sm"
            color="white"
            :trailing="false"
            placeholder="You will pay"
            :padder="false"
            variant="none"
          />
          <UButton @click="sendTransaction?.()"> aa</UButton>
          <!-- <UDropdown :items="items" :popper="{ placement: 'right-start' }">
            <UButton
              color="white"
              label="Options"
              trailing-icon="i-heroicons-chevron-down-20-solid"
              class="w-full"
              variant="ghost"

      
            />
          </UDropdown> -->
        </div>

        <template #footer>
          <UButton type="submit" :loading="false" block> Submit </UButton>
        </template>
      </UCard>
    </UForm>
  </UContainer>
</template>
<style>
.form-size {
  width: 600px;
}
</style>
