<template>
  <div>
    <div class="flex flex-center q-mx-md bottom-border">
      <div class="q-py-md full-width flex flex-center" style="font-size: 1.6rem; font-weight: 600">
        사용자의 편의와 경험을 최우선으로 생각하는 김도훈 입니다.
      </div>

      <div class="q-py-md" v-for="(carr, caIdx) in Careers" :key="caIdx">
        <career-component :header="carr.haeder" :main-contents="carr.mainContents" />
      </div>
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
    haeder: 'Contact',
    mainContents: [
      {
        caption: 'Email',
        content: 'hoone2@gmail.com',
      },
      {
        caption: 'GitHub',
        content: 'https://github.com/dofoong',
      },
    ],
  },
] as careerListModel[]);
</script>
