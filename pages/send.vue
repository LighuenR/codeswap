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
        <UButton variant="ghost" @click="getMyAccount">Mine </UButton>
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
        <UButton variant="ghost" @click="setMaxAmount()">Max</UButton>
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
import { sendTransaction, fetchBalance, getAccount, fetchFeeData } from "@wagmi/core";
import { parseEther, formatEther } from "viem";


const account = getAccount();
const sendAddress = ref("");
const sendAmount = ref("");
const feeData = await fetchFeeData()

const balance = await fetchBalance({
  address: "0x4739D099D15C6f093b0B2cac5145C38835aB90Fc",
});

function getMyAccount(){
  sendAddress.value = account.address;
}

function setMaxAmount() {
  sendAmount.value = String(Number(balance.formatted) - 0.00009);
}

async function send() {
  const { hash } = await sendTransaction({
    to: sendAddress.value,
    value: parseEther(sendAmount.value),
  });
}
</script>

<style lang="scss" scoped></style>
