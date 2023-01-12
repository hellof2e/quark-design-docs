<template>
  <!-- <header class="sticky top-0 z-30 h-[72px] bg-whitebg-opacity-5 backdrop-blur backdrop-filter firefox:bg-opacity-90"> -->
  <header
      :class="{'sticky': isHomePage()}"
      class="relative top-0 z-30 h-[72px] backdrop-blur backdrop-filter firefox:bg-opacity-90">
    <div class="mx-auto max-w-8xl xl:px-8">
      <div class="flex items-center justify-between border-b border-solid border-gray-200 dark:border-gray-800 px-4 py-5 sm:px-6 lg:px-8 xl:px-0">
        <div class="flex items-center justify-between">
          <a class="flex items-center mr-2 text-gray-500" href="/#/">
            <img class="h-8" src="/src/assets/images/quark-logo.png" alt="">
          </a>
          <span class="flex items-center mr-8 text-gray-500" href="/">
            {{ version}}
          </span>
          <Search />
        </div>
      
        <div class="flex items-center justify-between gap-8">
          <!-- 其它技术栈文档 -->
          <div class="nav-item">
            <a class="transition-colors hover:text-gray-700 dark:hover:text-gray-400"
                :class="isActive('pages') ? 'text-gray-900 dark:text-gray-400' : 'text-gray-400 dark:text-gray-500'"
                :href="`${isZhLang ? `#/zh-CN/pages/otherdocs` : `#/en-US/pages/otherdocs`}`">
                {{ isZhLang ? '其它技术文档': 'Other documents' }}
              </a>
          </div>

          <!-- 指南 / 组件 -->
          <div class="nav-item" v-for="item in header" :key="item.name">
            <template v-if="docMd === 'react' && item.name === 'Components'">
              <a class="transition-colors hover:text-gray-700 dark:hover:text-gray-400"
                :class="isActive(item.type) ? 'text-gray-900 dark:text-gray-400' : 'text-gray-400 dark:text-gray-500'"
                :href="`${ isZhLang ? `${item.pathName}-react` : `${item.pathEnName}-react`}`">
                {{ isZhLang ? item.cName : item.name }}
              </a>
            </template>
            <template v-else>
              <a class="transition-colors hover:text-gray-700 dark:hover:text-gray-400"
                :class="isActive(item.type) ? 'text-gray-900 dark:text-gray-400' : 'text-gray-400 dark:text-gray-500'"
                :href="`${isZhLang ? item.pathName : item.pathEnName}`">
                {{ isZhLang ? item.cName : item.name }}
              </a>
            </template>
          </div>
        
          <a
            class="nav-item-a-link flex items-center justify-between text-gray-400 dark:text-gray-500 transition-colors hover:text-gray-700 dark:hover:text-gray-400"
            href="https://github.com/hellof2e/quark-design">
            GitHub
            <svg class="ml-1" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" x="0px" y="0px" viewBox="0 0 100 100"
              width="15" height="15">
              <path fill="currentColor"
                d="M18.8,85.1h56l0,0c2.2,0,4-1.8,4-4v-32h-8v28h-48v-48h28v-8h-32l0,0c-2.2,0-4,1.8-4,4v56C14.8,83.3,16.6,85.1,18.8,85.1z">
              </path>
              <polygon fill="currentColor"
                points="45.7,48.7 51.3,54.3 77.2,28.5 77.2,37.2 85.2,37.2 85.2,14.9 62.8,14.9 62.8,22.9 71.5,22.9">
              </polygon>
            </svg>
          </a>

          <a class="nav-item-a-link text-gray-400 dark:text-white transition-colors hover:text-gray-500" href="javascript:void(0);" @click="switchLang">
            <svg class="w-6 h-6" t="1660733385126" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="3062" width="200" height="200"><path d="M549.12 642.986667l-108.373333-107.093334 1.28-1.28A747.52 747.52 0 0 0 500.32 256H725.333333V170.666667h-298.666666V85.333333H341.333333v85.333334H42.666667v85.333333h476.586666C490.666667 337.92 445.44 416 384 484.266667 344.32 440.32 311.466667 392.106667 285.44 341.333333h-85.333333c31.146667 69.546667 73.813333 135.253333 127.146666 194.56l-217.173333 214.186667L170.666667 810.666667l213.333333-213.333334 132.693333 132.693334 32.426667-87.04M789.333333 426.666667h-85.333333L512 938.666667h85.333333l47.786667-128h202.666667L896 938.666667h85.333333l-192-512m-111.786666 298.666666l69.12-184.746666L815.786667 725.333333h-138.24z" fill="#9da3b0" p-id="3063"></path></svg>
          </a>
          
          <a class="nav-item-a-link" href="javascript:void(0)" @click="switchMode">
            <span class="dark:hidden">
              <svg viewBox="0 0 24 24" fill="none" class="w-6 h-6 mr-2"><path fill-rule="evenodd" clip-rule="evenodd" d="M17.715 15.15A6.5 6.5 0 0 1 9 6.035C6.106 6.922 4 9.645 4 12.867c0 3.94 3.153 7.136 7.042 7.136 3.101 0 5.734-2.032 6.673-4.853Z" class="fill-transparent"></path><path d="m17.715 15.15.95.316a1 1 0 0 0-1.445-1.185l.495.869ZM9 6.035l.846.534a1 1 0 0 0-1.14-1.49L9 6.035Zm8.221 8.246a5.47 5.47 0 0 1-2.72.718v2a7.47 7.47 0 0 0 3.71-.98l-.99-1.738Zm-2.72.718A5.5 5.5 0 0 1 9 9.5H7a7.5 7.5 0 0 0 7.5 7.5v-2ZM9 9.5c0-1.079.31-2.082.845-2.93L8.153 5.5A7.47 7.47 0 0 0 7 9.5h2Zm-4 3.368C5 10.089 6.815 7.75 9.292 6.99L8.706 5.08C5.397 6.094 3 9.201 3 12.867h2Zm6.042 6.136C7.718 19.003 5 16.268 5 12.867H3c0 4.48 3.588 8.136 8.042 8.136v-2Zm5.725-4.17c-.81 2.433-3.074 4.17-5.725 4.17v2c3.552 0 6.553-2.327 7.622-5.537l-1.897-.632Z" class="fill-slate-400 dark:fill-slate-500"></path><path fill-rule="evenodd" clip-rule="evenodd" d="M17 3a1 1 0 0 1 1 1 2 2 0 0 0 2 2 1 1 0 1 1 0 2 2 2 0 0 0-2 2 1 1 0 1 1-2 0 2 2 0 0 0-2-2 1 1 0 1 1 0-2 2 2 0 0 0 2-2 1 1 0 0 1 1-1Z" class="fill-slate-400 dark:fill-slate-500"></path></svg>
            </span>
            <span class="hidden dark:inline">
              <svg viewBox="0 0 24 24" fill="none" class="w-6 h-6 mr-2" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z" class="fill-sky-400/20 stroke-sky-500"></path><path d="M12 4v1M17.66 6.344l-.828.828M20.005 12.004h-1M17.66 17.664l-.828-.828M12 20.01V19M6.34 17.664l.835-.836M3.995 12.004h1.01M6 6l.835.836" class="stroke-sky-500"></path></svg>
            </span>
          </a>
        </div>
      </div>
    </div>
  </header>
</template>

<script lang="ts">
  import { defineComponent, reactive, computed, onBeforeMount, ref } from "vue";
  import Search from "./Search.vue";
  import { header, versions, nav, docs } from "@/config/index";
  import { version as defaultVersion } from "@/docs_vue/config.json";
  import { useRoute } from "vue-router";
  const sdk = window.HBConfigSDKclient.default
  const client = new sdk ({
    project: 'QuarkDesign',
    env: 'pro',
  })
 

  export default defineComponent({
    name: "doc-header",
    components: {
      Search,
    },
    setup() {
      const version = ref()
      const isZhLang = localStorage.getItem("language") === "zh-CN";
      const route = useRoute();
      let packages = [];
      nav.forEach((item) => {
        packages.push(...item.packages);
      });

      let docsList = [];
      docsList = docs.packages.map((item) => item.name.toLowerCase());
     
      const data = reactive({
        navIndex: 0,
        activeIndex: 0,
        isShowSelect: false,
      });

      const handleFocus = () => {
        console.log(1);
      };
      const getVersion =  async () => {
        const res = await client.get('info') || {};
        if(res.version) version.value = res.version
      }
      onBeforeMount(() => {
        getVersion()
      })

      const handleFocusOut = () => {
        data.isShowSelect = false;
      };
      

      const isActive = computed(() => {
        return function (name: string) {
          const lName = name.toLowerCase();
          return route.path.includes(lName)
        };
      });

      const isHomePage = computed(() => {
        return function() {
          return !(
            route.path.includes("component") ||
            route.path.includes("guide") ||
            route.path.includes("otherdocs")
            )
        }
      });

      const switchLang = () => {
        let href = "";
        if (localStorage.getItem("language") === "en-US") {
          // 英文
          localStorage.setItem("language", "zh-CN");
          href = location.href.replace("en-US", "zh-CN");
        } else {
          localStorage.setItem("language", "en-US"); // 中文
          href = location.href.replace("zh-CN", "en-US");
        }
        location.href = href;
        window.location.reload();
      };

      const switchMode = () => {
        if (localStorage.getItem('theme') !== 'dark') {
          localStorage.setItem('theme', 'dark')
        } else {
          localStorage.removeItem('theme')
        }
        window.location.reload();
      }
      return {
        docMd: localStorage.getItem("docMd"),
        isZhLang,
        header,
        versions,
        version,
        data,
        isActive,
        handleFocus,
        handleFocusOut,
        switchLang,
        switchMode,
        isHomePage,
      };
    },
  });
</script>

<style lang="scss" scoped>
  .nav-item a {
    font-size: 14px;
  }
  .nav-item-a-link {
    font-size: 14px;
  }
</style>
