<script setup>
const props = defineProps(['items', 'label'])
const emit = defineEmits(['val'])
function emitValue(event) {
  emit('val', event.target.value)
}
</script>

<template>
  <div class="custom-form-element">
    <label for="exampleFormControlInput1">{{ props.label }}</label>
    <select class="form-select" aria-label="Default select example" @change="emitValue">
      <option v-for="item in props.items" :key="item.label" :value="item.id">
        {{ item.name }}
      </option>
    </select>
  </div>
</template>
