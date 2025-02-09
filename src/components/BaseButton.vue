<script setup>
const props = defineProps({
  type: { type: String, default: 'button' },
  label: { type: String, required: true },
  color: { type: String, default: 'primary' },
  outline: { type: Boolean, default: false },
  icon: { type: String }
})
const emit = defineEmits(['click'])
</script>
\
<template>
  <button
    class="btn"
    :class="[props.outline ? `btn-outline-${props.color}` : `btn-${props.color}`]"
    @click="emit('click')"
  >
    <i v-if="props.icon" class="me-1 bi" :class="`bi-${icon}`"></i>
    {{ props.label }}
  </button>
</template>

<style scoped>
.btn {
  margin: 1rem 4px 1rem;
}
</style>

<!-- Icon list at https://icons.getbootstrap.com/ -->
