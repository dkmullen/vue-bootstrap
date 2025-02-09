<script setup>
const props = defineProps({ items: Array, id: String })
</script>
<template>
  <!-- Currently set to show the first item as open and the others closed using the classes 'collapsed' and 'show' -->
  <div class="accordion" :id="props.id">
    <div class="accordion-item" v-for="(item, index) in props.items" :key="item.title">
      <h2 class="accordion-header">
        <button
          class="accordion-button"
          :class="{ collapsed: index !== 0 }"
          type="button"
          data-bs-toggle="collapse"
          :data-bs-target="`#collapse${index}`"
          :aria-expanded="index === 0 ? true : false"
          :aria-controls="`collapse${index}`"
        >
          {{ item.title }}
        </button>
      </h2>
      <div
        :id="`collapse${index}`"
        class="accordion-collapse collapse"
        :class="{ show: index === 0 }"
        :data-bs-parent="`${props.id}`"
      >
        <div class="accordion-body" v-html="item.bodyText"></div>
      </div>
    </div>
  </div>
</template>
