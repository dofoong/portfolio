<template>
  <div class="row" style="width: 1200px">
    <div class="header col-3 row items-center" style="font-size: 2rem; color: darkslateblue">
      <div
        style="width: 5px; background-color: darkslateblue; height: calc(100% - 20px)"
        class="q-mr-sm"
      ></div>
      <div>
        {{ props.header }}
      </div>
    </div>
    <div class="main col">
      <div class="row" v-for="(con, cIdx) in props.mainContents" :key="cIdx">
        <div
          class="caption q-mx-sm q-mb-sm q-px-sm"
          ref="captionRef"
          :style="{ minWidth: captionWidth + 'px' }"
          style="border-radius: 10px; border: 1px solid grey; color: grey"
        >
          {{ con.caption }}
        </div>
        <div class="content">
          {{ con.content }}
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { nextTick, onMounted, ref } from 'vue';
import type { PropType } from 'vue';
import type { CareerMainContents } from './Career.types';

const props = defineProps({
  header: {
    type: String,
    required: true,
  },
  mainContents: {
    type: Array as PropType<CareerMainContents[]>,
    required: true,
  },
});

const captionRef = ref([] as HTMLDivElement[]);
const captionWidth = ref(0);

function getCaptionWidth() {
  captionRef.value.forEach((item: HTMLDivElement) => {
    const offsetWidth: number = item.offsetWidth;
    if (captionWidth.value < offsetWidth) {
      captionWidth.value = offsetWidth;
    }
  });
}

onMounted(async () => {
  await nextTick();
  getCaptionWidth();
});
</script>
