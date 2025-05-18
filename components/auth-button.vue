<script setup lang="ts">
import { createAuthClient } from "better-auth/client";

const authClient = createAuthClient();

async function signIn() {
  await authClient.signIn.social({
    provider: "google",
    callbackURL: "/dashboard",
  });
}
</script>

<template>
  <button class="btn btn-accent" @click="signIn">
    Sign In With Google
    <Icon name="tabler:brand-google-filled" size="24" />
  </button>
</template>
