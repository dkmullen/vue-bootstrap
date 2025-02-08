<script setup>
import BaseSelect from './components/BaseSelect.vue'
import BaseInput from './components/BaseInput.vue'
import AccordianView from './components/AccordianView.vue'

const items = ['Uno', 'Dos', 'Tres']
</script>

<template>
  <main>
    <BaseSelect :items="items" @val="showMe" label="Pick one" />
    <BaseInput label="Email" />
    <AccordianView />
  </main>
</template>
