<script setup>
import { Head, Link } from "@inertiajs/vue3";

defineProps({
  canLogin: Boolean,
  canRegister: Boolean,
  laravelVersion: String,
  phpVersion: String,
});
</script>

<template>
  <Head title="Welcome" />

  <div
    class="
      tw-relative tw-flex
      items-top
      tw-justify-center tw-min-h-screen tw-bg-gray-100
      dark:tw-bg-gray-900
      sm:tw-items-center sm:tw-pt-0
    "
  >
    <div
      v-if="canLogin"
      class="tw-hidden tw-fixed tw-top-0 tw-right-0 tw-px-6 tw-py-4 sm:tw-block"
    >
      <Link
        v-if="$page.props.user"
        :href="route('dashboard')"
        class="tw-text-sm tw-text-gray-700 dark:tw-text-gray-500 tw-underline"
        >Dashboard</Link
      >

      <template v-else>
        <Link
          :href="route('login')"
          class="tw-text-sm tw-text-gray-700 dark:tw-text-gray-500 tw-underline"
          >Log in</Link
        >

        <Link
          v-if="canRegister"
          :href="route('register')"
          class="
            tw-ml-4 tw-text-sm tw-text-gray-700
            dark:tw-text-gray-500
            tw-underline
          "
          >Register</Link
        >
      </template>
    </div>
    <div class="card" style="width: 18rem">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
        <p class="card-text">
          Some quick example text to build on the card title and make up the
          bulk of the card's content.
        </p>
        <a href="#" class="card-link">Card link</a>
        <a href="#" class="card-link">Another link</a>
      </div>
    </div>
  </div>
</template>
