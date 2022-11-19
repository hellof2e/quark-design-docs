<template>
  <div
    v-if="isShowSideBar()"
    class="doc-nav w-[260px] border-r border-solid border-gray-200 dark:border-gray-800 overflow-auto fixed left-0 bottom-0 z-10 transition-all"
    :class="{ 'fixed-class': fixed }">
    
    <!-- Doc‘s Switch -->
    <div class="sticky bg-white dark:bg-gray-900 top-0 pt-4 px-2 z-[1]">
      <div v-if="isShow()" class="grid items-center justify-between h-[40px] rounded bg-zinc-100 dark:bg-gray-700 px-1 grid-cols-2">
        <div
          :class="curKey === item.key ? 'bg-white dark:bg-gray-900' : 'bg-zinc-100 dark:bg-gray-700 dark:text-gray-400'"
          :key="item.key"
          class="tab-item relative px-[10px] leading-8 cursor-pointer text-base rounded text-center dark:text-gray-400"
          v-for="item in tabs"
          @click="handleTabs(item.key)"
        >
          {{ item.text }}
        </div>
      </div>
    </div>
    <div v-if="isShow()" class="sticky top-[56px] px-8 z-[1] h-8 bg-gradient-to-b from-white dark:from-slate-900"></div>

    <!-- Docs' nav -->
    <ol class="pl-[32px] mb-6 dark:text-gray-400" v-if="isGuideNav">
      <ul>
        <li
          :class="{ active: isActive(_package.name) }"
          v-for="_package in docs.packages"
          :key="_package"
          v-show="_package.show"
        >
          <router-link :to="_package.name.toLowerCase()" class="dark:text-gray-400">
            {{ isZhLang ? _package.cName : _package.name }}
          </router-link>
        </li>
      </ul>
    </ol>
    
    <!-- Components' nav -->
    <template v-else>
      <ol class="pl-[32px] mb-6 dark:text-gray-400" v-for="_nav in nav" :key="_nav">
        <li>{{ isZhLang ? _nav.name : _nav.enName }}</li>
        <ul>
          <template
            :class="{ active: isActive(_package.name) }"
            v-for="_package in reorder(_nav.packages)"
            :key="_package"
          >
            <li v-if="_package.show">
              <router-link
                :to="docMd === 'vue'? _package.name.toLowerCase() : `${_package.name.toLowerCase()}-react`"
                :class="{ 'active': isActive(_package.name) }"
                class="dark:text-gray-400 dark:dark-router-link-active"
              >
                {{ _package.name }}&nbsp;&nbsp;<b v-if="isZhLang">{{_package.cName}}</b>
              </router-link>
            </li>
          </template>
        </ul>
      </ol>
    </template>
  </div>
</template>

<script lang="ts">
import {
  defineComponent,
  reactive,
  computed,
  onMounted,
  toRefs,
} from "vue";
import { useRoute, useRouter, onBeforeRouteUpdate } from "vue-router";
import { RefData } from "@/assets/util/ref";
import { nav, docs } from "@/config";

export default defineComponent({
  name: "DocNav",
  props: {
    fixed: Boolean,
  },
  setup() {
    const route = useRoute();
    const router = useRouter();
    const state = reactive({
      // fixed: false,
      isGuideNav: false,
    });

    const docMd = localStorage.getItem("docMd");
    const data = reactive({
      demoUrl: "demo.html",
      curKey: docMd,
      tabs: [
        {
          key: "vue",
          text: "vue",
        },
        {
          key: "react",
          text: "react",
        },
      ],
    });

    const isShow = () => {
      return !route.path.includes("guide");
    };

    const isShowSideBar = () => {
      return !(route.path.includes('pages'));
    }

    const isActive = computed(() => {
      return function (name: string) {
        const currentValue = RefData.getInstance().currentRoute.value;
        const value = currentValue;
        return value == name.toLowerCase();
      };
    });

    const watchDocMd = (curKey: string) => {
      const path = route.path;
      if (curKey.includes("react")) {
        router.replace(`${path}-react`);
      } else {
        router.replace(path.substr(0, path.length - 6));
      }
      setTimeout(() => {
        window.location.reload();
      }, 500);
    };

    const handleTabs = (curKey: string) => {
      if(curKey === data.curKey) return;
      data.curKey = curKey;
      localStorage.setItem("docMd", curKey);
      watchDocMd(curKey);
    };


    const reorder = (packages: any) => {
      return packages.sort(function (x: any, y: any) {
        return x["name"].localeCompare(y["name"]);
      });
    };

    onMounted(() => {
      if (route.path) getIsGuaid(route.path);
    });

    const getIsGuaid = (path: string) => {
      state.isGuideNav = path.indexOf("guide") > -1;
    };

    onBeforeRouteUpdate((to: any) => {
      getIsGuaid(to.path);
    });

    return {
      ...toRefs(data),
      ...toRefs(state),
      isZhLang: localStorage.getItem("language") === "zh-CN",
      isActive,
      docMd: localStorage.getItem("docMd"),
      nav: reactive(nav),
      docs: reactive(docs),
      reorder,
      isShow,
      isShowSideBar,
      handleTabs,
    };
  },
});
</script>

<style lang="scss">
.doc-nav {
  top: 75px;
  &.fixed-class {
    top: 0;
  }
  ol {
    margin-bottom: 20px;
    li {
      font-size: 14px;
      font-weight: bold;
      position: relative;

      &.active {
        &::before {
          position: absolute;
          content: "";
          left: 0;
          top: 50%;
          width: 22px;
          margin-top: -5px;
          height: 10px;
          transform: rotate(90deg);
        }
      }
    }

    > ul {
      li {
        padding-left: 29px;
        cursor: pointer;

        &:hover {
          a {
            color: #38bdf8;
          }
        }

        a {
          height: 48px;
          line-height: 48px;
          display: flex;

          &.router-link-active,
          &.active {
            color: #38bdf8;
          }

          &:hover {
            color: #38bdf8;

            &:visited {
              color: #38bdf8;
            }
          }
          
          b {
            font-weight: normal;
            font-size: 12px;
          }
        }
      }
    }
  }
}
</style>
