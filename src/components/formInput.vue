<script lang="ts">
export default {
  props: ['modelValue']
}
</script>

<template>
  <input
    class="w-[445px] h-[40px] border rounded-lg py-[16px] px-[24px] placeholder:font-[400] placeholder:text-[#667499] placeholder:text-[14px] border-[#C2C7D6] hover:bg-[#F6F7F9]/50 outline-none focus:bg-[#F6F7F9]"
    :value="modelValue"
    type="text"
    @input="$emit('update:modelValue', ($event.target as HTMLInputElement).value)"
    v-bind="$attrs"
  />
</template>
