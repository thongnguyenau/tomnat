<script setup>
import ApplicationLogo from "@/Components/ApplicationLogo.vue";
</script>

<template>
  <div>
    <div class="tw-p-6 sm:tw-px-20 tw-bg-white tw-border-b tw-border-gray-200">
      <div>
        <ApplicationLogo class="tw-block tw-h-12 tw-w-auto" />
      </div>

      <div class="tw-mt-8 tw-text-2xl">
        {{ $page.props.locale }}
      </div>
    </div>
  </div>
</template>
