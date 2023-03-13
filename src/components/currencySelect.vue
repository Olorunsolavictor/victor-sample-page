<script lang="ts">
export default {
  props: ['modelValue']
}
</script>

<template>
  <select
    required
    placeholder=""
    :value="modelValue"
    @input="$emit('update:modelValue', ($event.target as HTMLInputElement).value)"
    v-bind="$attrs"
    class="w-[108px] h-[39px] bg-[#080056] rounded-[4px] text-white text-[14px] px-[14px] py-[10px] outline-none hover:bg-[#080056]/80"
  >
    <option value="">$</option>
    <option>₦</option>
    <option>£</option>
    <option>¢</option>
  </select>
</template>
