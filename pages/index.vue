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
  [
    {
      label: "Edit",
      icon: "i-heroicons-pencil-square-20-solid",
      shortcuts: ["E"],
      click: () => {
        console.log("Edit");
      },
    },
    {
      label: "Duplicate",
      icon: "i-heroicons-document-duplicate-20-solid",
      shortcuts: ["D"],
      disabled: true,
    },
  ],
  [
    {
      label: "Archive",
      icon: "i-heroicons-archive-box-20-solid",
    },
    {
      label: "Move",
      icon: "i-heroicons-arrow-right-circle-20-solid",
    },
  ],
  [
    {
      label: "Delete",
      icon: "i-heroicons-trash-20-solid",
      shortcuts: ["⌘", "D"],
    },
  ],
];
</script>

<template>
  <UContainer class="flex flex-col gap-4 w-96 mt-8">
    <UForm>
      <UCard>
        <template #header>
          <div class="grid grid-cols-2">
            <div class="grid grid-cols-2 gap-4">
              <h1>Comprar</h1>
              <h1>Vender</h1>
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

          <UDropdown :items="items" :popper="{ placement: 'bottom-start' }">
            <UButton
              color="white"
              label="Options"
              variant="ghost"
              icon="i-heroicons-light-bulb"
            />
          </UDropdown>
        </div>
        <UDivider icon="i-heroicons-arrow-long-down" class="my-2"/>
        <div class="grid grid-cols-2 gap-1">
          <UInput
            class="mt-2 w-full"
            icon="i-heroicons-magnifying-glass-20-solid"
            size="sm"
            color="white"
            :trailing="false"
            placeholder="You will pay"
            :padder="false"
            variant="none"
          />

          <UDropdown :items="items" :popper="{ placement: 'bottom-start' }">
            <UButton
              color="white"
              label="Options"
              variant="ghost"
              icon="i-heroicons-light-bulb"
            />
          </UDropdown>
        </div>
        <template #footer>
          <UButton type="submit" :loading="false" block> Submit </UButton>
        </template>
      </UCard>
    </UForm>
  </UContainer>
</template>
