<script setup>
import BaseSelect from './components/BaseSelect.vue'
import BaseInput from './components/BaseInput.vue'
import AccordianView from './components/AccordianView.vue'
import BaseButton from './components/BaseButton.vue'

const items = ['Uno', 'Dos', 'Tres']
const accordianItems = [
  { title: 'Check One', bodyText: '<strong>Item one</strong> is a good one.' },
  { title: 'Check Two', bodyText: '<strong>Item 2</strong> is a good one.' },
  { title: 'Check Three', bodyText: '<strong>Item 3</strong> is a good one.' }
]
function logButtonMsg(message) {
  console.log(message)
}
</script>

<template>
  <main>
    <BaseSelect :items="items" label="Pick one" />
    <BaseInput label="Email" />
    <AccordianView :items="accordianItems" id="myAccordian" />
    <BaseButton label="Click Me" color="success" @click="logButtonMsg('Success!')" />
    <BaseButton
      label="Wha?"
      color="primary"
      :outline="true"
      @click="logButtonMsg('Wha?')"
      icon="alarm"
    />
  </main>
</template>
