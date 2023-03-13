<script lang="ts">
export default {
  name: 'myButton',
  props: {
    type: {
      type: String,
      default: 'save'
    }
  }
}
</script>

<template>
  <button
    type="submit"
    class="w-[148px] h-[40px] font-[700] text-[#080056] text-[16px] rounded-[12px] border border-[#080056] hover:opacity-80 focus:outline-none"
  >
    <slot />
  </button>
</template>
