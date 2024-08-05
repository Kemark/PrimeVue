<template>

 <component :is="isClickable ? 'a' : PassThroughx" href="http://deka.de">
  <VueCard>
    <template #title>{{ title }}</template>
    <template #content>
      <p class="m-0">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore sed
        consequuntur error repudiandae numquam deserunt quisquam repellat libero
        asperiores earum nam nobis, culpa ratione quam perferendis esse,
        cupiditate neque quas!
      </p>
    </template>
  </VueCard>
</component>

</template>

<script setup lang="ts">
import { ref, defineComponent, h } from 'vue';
import VueCard from 'primevue/card';
import PassThrough from './PassThrough.vue';

const props = defineProps({
  isClickable: Boolean,
  title: String
})

const PassThroughx = defineComponent({
  name: 'PassThroughx',
  setup(_, { slots }) {
  return () => {
          // xxx xxx xxx xxx xxx
          return slots.default ? h(slots.default()) : null;
        };
  },
});
</script>

<style scoped></style>
