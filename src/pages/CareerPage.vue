<template>
  <div>
    <div class="flex flex-center q-mx-md">
      <career-component
        v-for="(carr, caIdx) in Careers"
        :key="caIdx"
        :header="carr.haeder"
        :main-contents="carr.mainContents"
      />
    </div>
  </div>
</template>
<script setup lang="ts">
import { ref } from 'vue';
import CareerComponent from 'src/components/CareerComponent.vue';
import type { CareerMainContents } from 'src/components/Career.types';

export interface careerListModel {
  haeder: string;
  mainContents: CareerMainContents[];
}

const Careers = ref([
  {
    haeder: 'PROFILE',
    mainContents: [
      {
        caption: 'CAPTION test4',
        content: 'CONTENT test1',
      },
      {
        caption: 'CAPTION test4545454',
        content: 'CONTENT test2',
      },
    ],
  },
] as careerListModel[]);
</script>
