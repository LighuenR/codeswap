<template>
  <UContainer class="flex flex-col gap-4 form-size mt-8">
    <UCard class="mt-4">
      <template #header>
        <h1 class="text-xl">Send Tokens</h1>
      </template>
      <UFormGroup label="Address">
        <UInput
          v-model="sendAddress"
          class="w-full"
          size="sm"
          color="white"
          :trailing="false"
          placeholder="0x..."
          :padder="false"
          variant="none"
        />
      </UFormGroup>

      <UDivider icon="i-heroicons-arrow-long-down" class="my-2" />
      <UFormGroup label="Amount">
        <UInput
          v-model="sendAmount"
          class="w-full"
          size="sm"
          color="white"
          :trailing="false"
          placeholder="Amount"
          :padder="false"
          variant="none"
        />
      </UFormGroup>
      <template #footer>
        <UButton type="submit" :loading="false" block @click="send()">
          Submit
        </UButton>
      </template>
    </UCard>
  </UContainer>
</template>

<script setup>
import { sendTransaction } from "@wagmi/core";
import { parseEther } from "viem";

const sendAddress = ref("");
const sendAmount = ref("");

async function send() {
  const { hash } = await sendTransaction({
    to: sendAddress.value,
    value: parseEther(sendAmount.value),
  });
}
</script>

<style lang="scss" scoped></style>
