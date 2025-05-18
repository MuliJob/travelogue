<script setup lang="ts">
import { createAuthClient } from "better-auth/client";

const authClient = createAuthClient();
const loading = ref(false);

async function signIn() {
  loading.value = true;
  await authClient.signIn.social({
    provider: "google",
    callbackURL: "/dashboard",
  });
  loading.value = false;
}
</script>

<template>
  <button :disabled="loading" class="btn btn-accent" @click="signIn">
    <span v-if="loading" class="text-gray-950 loading loading-dots loading-md" />
    <template v-else>
      Sign In With Google
      <Icon name="tabler:brand-google-filled" size="24" />
    </template>
  </button>
</template>
