<script setup>
import { onMounted, ref } from "vue";

defineProps({
  modelValue: String,
});

defineEmits(["update:modelValue"]);

const input = ref(null);

onMounted(() => {
  if (input.value.hasAttribute("autofocus")) {
    input.value.focus();
  }
});

defineExpose({ focus: () => input.value.focus() });
</script>

<template>
  <input
    ref="input"
    class="
      tw-border-gray-300
      focus:tw-border-indigo-300
      focus:tw-ring
      focus:tw-ring-indigo-200
      focus:tw-ring-opacity-50
      tw-rounded-md tw-shadow-sm
    "
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  />
</template>
