<template>
  <q-layout>
    <div style="height: 50px">
      <q-toolbar class="flex flex-center" :class="pageScroll ? 'dragNav' : 'normalNav'">
        <div class="row items-center full-width" style="max-width: 1200px">
          <q-toolbar-title class="cursor-pointer header-font" @click="$router.push('/')">
            HOME
          </q-toolbar-title>
          <q-space></q-space>
          <div
            class="q-mx-md cursor-pointer xs-hide header-font"
            style="font-size: 1.4rem"
            v-for="(menu, mIdx) in essentialLinks"
            :key="mIdx"
            @click="menu.anchor ? openPage(menu.link) : $router.push(menu.link ? menu.link : '')"
          >
            {{ menu.title }}
          </div>
          <q-btn
            flat
            dense
            round
            icon="menu"
            aria-label="Menu"
            class="cursor-pointer xl-hide lg-hide md-hide sm-hide"
            @click="toggleLeftDrawer"
          />
        </div>
      </q-toolbar>
    </div>

    <div class="row" ref="sideBarElement" @resize="handleResize">
      <div
        style="width: calc((100% - 1200px) / 2); height: calc(100vh - 50px)"
        v-show="useSideBar"
      ></div>
      <div class="row full-width" style="max-width: 1200px">
        <q-page-container>
          <router-view />
        </q-page-container>
      </div>
      <div
        style="width: calc((100% - 1200px) / 2); height: calc(100vh - 50px)"
        v-show="useSideBar"
      ></div>
    </div>
  </q-layout>
</template>

<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue';
import type { LinkProps } from './Layout.model';

const pageScroll = ref(false);
const scrollThrottle = ref(false);
const useSideBar = ref(false);

const essentialLinks: LinkProps[] = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'Docs',
    anchor: false,
  },
  {
    title: 'Career',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'Career',
    anchor: false,
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/dofoong',
    anchor: true,
  },
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}

function genDragHeight() {
  if (!scrollThrottle.value) {
    scrollThrottle.value = true;
    if (window.scrollY > 50) {
      pageScroll.value = true;
    } else {
      pageScroll.value = false;
    }

    setTimeout(() => {
      scrollThrottle.value = false;
    }, 10);
  }
}

function openPage(href?: string) {
  window.open(href, '_blank');
}

const sideBarElement = ref(null as HTMLDivElement | null);

const addResizeListener = () => {
  window.addEventListener('resize', handleResize);
};

const removeResizeListener = () => {
  window.removeEventListener('resize', handleResize);
};

// 컴포넌트가 마운트된 후에 이벤트 리스너 등록
onMounted(() => {
  addResizeListener();
});

// 컴포넌트가 언마운트되기 전에 이벤트 리스너 제거
onBeforeUnmount(() => {
  removeResizeListener();
});

// 크기 변경 이벤트 핸들러
const handleResize = () => {
  if (sideBarElement.value == null) {
    return;
  }
  const targetElement = Number(sideBarElement.value.clientWidth);
  if (targetElement > 1400) {
    useSideBar.value = true;
  } else {
    useSideBar.value = false;
  }
};

onMounted(() => {
  document.addEventListener('scroll', genDragHeight);
  handleResize();
});
</script>
<style lang="scss" scoped>
.dragNav {
  position: fixed;
  top: 0px;
  border-bottom: 1px solid rgba(73, 73, 73, 0.363);
  background-color: white;
  // background-color: rgb(54, 51, 51);
  // color: white;
  z-index: 999;
}
</style>
