<script setup>
const props = defineProps(['label'])
const emit = defineEmits(['val'])
function emitValue(event) {
  emit('val', event.target.value)
}
</script>

<template>
  <div class="custom-form-element">
    <label for="exampleFormControlInput1">{{ props.label }}</label>
    <input
      type="email"
      class="form-control"
      id="exampleFormControlInput1"
      placeholder="name@example.com"
      @change="emitValue"
    />
  </div>
</template>
