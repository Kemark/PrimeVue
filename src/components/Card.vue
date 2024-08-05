<template>

 <component :is="isClickable ? 'a' : 'PassThrough'" href="asdf">hallo
 adsfasd
 fromadf
 adsfasd
 </component>

<a href="https://spiegel.de">
  <VueCard>
    <template #title>Simple Card</template>
    <template #content>
      <p class="m-0">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore sed
        consequuntur error repudiandae numquam deserunt quisquam repellat libero
        asperiores earum nam nobis, culpa ratione quam perferendis esse,
        cupiditate neque quas!
      </p>
    </template>
  </VueCard>
  </a>
</template>

<script setup lang="ts">
import { ref, defineComponent, h } from 'vue';
import VueCard from 'primevue/card';

const props = defineProps({
  isClickable: Boolean
})

const PassThrough = defineComponent({
  name: 'PassThrough',
  setup(_, { slots }) {
    return () => slots.default ? h(slots.default()) : null;
  },
});
</script>

<style scoped></style>
