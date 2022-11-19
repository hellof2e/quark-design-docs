<template>
  <div class="overflow-hidden">
    <div class="border-t border-gray-700 bg-gradient dark:dark-bg-gradient">
      <div
        class="grid w-full grid-cols-[12px,1fr,12px] gap-px sm:grid-cols-[19px,1fr,14px,1fr,19px] lg:grid-cols-[19px,1fr,14px,1fr,14px,1fr,19px] xl:grid-cols-[minmax(19px,1fr),minmax(286px,322px),30px,minmax(286px,322px),30px,minmax(286px,322px),30px,minmax(286px,322px),minmax(19px,1fr)]">
        <div class="h-3 bg-white dark:bg-gray-900"></div>
        <div class="h-3 bg-white dark:bg-gray-900"></div>
        <div class="h-3 bg-white dark:bg-gray-900"></div>
        <div class="hidden h-3 bg-white dark:bg-gray-900 sm:block"></div>
        <div class="hidden h-3 bg-white dark:bg-gray-900 sm:block"></div>
        <div class="hidden h-3 bg-white dark:bg-gray-900 lg:block"></div>
        <div class="hidden h-3 bg-white dark:bg-gray-900 lg:block"></div>
        <div class="hidden h-3 bg-white dark:bg-gray-900 xl:block"></div>
        <div class="hidden h-3 bg-white dark:bg-gray-900 xl:block"></div>

        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>

        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-2
          sm:col-start-2 sm:row-start-2
          lg:col-start-2 lg:row-start-2
          xl:col-start-2 xl:row-start-2
        ">
          <a :href="isZhLang ? `#/zh-CN/component/button${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/button${docMd === 'react' ? '-react' : ''}`">
            <img class="w-full" src="https://m.hellobike.com/resource/helloyun/13459/Q0l2mNZ_ek.svg" alt="">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-3
          sm:col-start-2 sm:row-start-3
          lg:col-start-2 lg:row-start-3
          xl:col-start-2 xl:row-start-3
        ">
          <a class=" text-gray-900 dark:text-white"
            :href="isZhLang ? `#/zh-CN/component/button${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/button${docMd === 'react' ? '-react' : ''}`">
            {{ `${isZhLang ? 'Button (按钮)' : 'Button' }`}}
          </a>
        </div>

        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:hidden
            xl:hidden
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:hidden
            xl:hidden
          "></div>

        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-4
          sm:col-start-4 sm:row-start-2
          lg:col-start-4 lg:row-start-2
          xl:col-start-4 xl:row-start-2
        ">
          <a :href="isZhLang ? `#/zh-CN/component/loading${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/loading${docMd === 'react' ? '-react' : ''}`">
            <img class="w-full" src="https://m.hellobike.com/resource/helloyun/13459/ud2vE_loading.svg" alt="">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-5
          sm:col-start-4 sm:row-start-3
          lg:col-start-4 lg:row-start-3
          xl:col-start-4 xl:row-start-3
        ">
          <a class=" text-gray-900 dark:text-white" :href="isZhLang ? `#/zh-CN/component/button${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/button${docMd === 'react' ? '-react' : ''}`">
            {{ `${isZhLang ? 'Loading (加载动画)' : 'Loading'}`}}
          </a>
        </div>

        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:hidden
            xl:hidden
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:hidden
            xl:hidden
          "></div>

        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-6
          sm:col-start-2 sm:row-start-4
          lg:col-start-6 lg:row-start-2
          xl:col-start-6 xl:row-start-2
        ">
          <a :href="isZhLang ? `#/zh-CN/component/switch${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/switch${docMd === 'react' ? '-react' : ''}`">
            <img src="https://m.hellobike.com/resource/helloyun/13459/x9Y7K_3switch.svg" alt="" class="w-full">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-7
          sm:col-start-2 sm:row-start-5
          lg:col-start-6 lg:row-start-3
          xl:col-start-6 xl:row-start-3
        ">
          <a class=" text-gray-900 dark:text-white"
            :href="isZhLang ? '#/zh-CN/component/button' : '#/en-US/component/button'">
            {{ `${isZhLang ? 'Switch (开关)' : 'Switch' }`}}
          </a>
        </div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:hidden
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:hidden
          "></div>

        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-8
          sm:col-start-4 sm:row-start-4
          lg:col-start-2 lg:row-start-4
          xl:col-start-8 xl:row-start-2
        ">
          <a :href="isZhLang ? `#/zh-CN/component/tab${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/tab${docMd === 'react' ? '-react' : ''}`">
            <img src="https://m.hellobike.com/resource/helloyun/13459/m0RKB_tab.svg" alt="" class="w-full">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-9
          sm:col-start-4 sm:row-start-5
          lg:col-start-2 lg:row-start-5
          xl:col-start-8 xl:row-start-3
        ">
          <a class=" text-gray-900 dark:text-white"
            :href="isZhLang ? `#/zh-CN/component/tab${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/tab${docMd === 'react' ? '-react' : ''}`">
            {{ `${isZhLang ? 'Tab (标签)' : 'Tab'}`}}
          </a>
        </div>

        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:hidden
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:hidden
            xl:block
          "></div>

        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-10
          sm:col-start-2 sm:row-start-6
          lg:col-start-4 lg:row-start-4
          xl:col-start-2 xl:row-start-4
        ">
          <a :href="isZhLang ? `#/zh-CN/component/cell${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/cell${docMd === 'react' ? '-react' : ''}`">
            <img src="https://m.hellobike.com/resource/helloyun/13459/sQvpz_cell.svg" alt="" class="w-full">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-11
          sm:col-start-2 sm:row-start-7
          lg:col-start-4 lg:row-start-5
          xl:col-start-2 xl:row-start-5
        ">
          <a class=" text-gray-900 dark:text-white"
            :href="isZhLang ? `#/zh-CN/component/cell${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/cell${docMd === 'react' ? '-react' : ''}`">
            {{ `${isZhLang ? 'Cell (单元格)' : 'Cell'}`}}
          </a>
        </div>

        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:hidden
            xl:hidden
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:hidden
            xl:hidden
          "></div>
          
        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-12
          sm:col-start-4 sm:row-start-6
          lg:col-start-6 lg:row-start-4
          xl:col-start-4 xl:row-start-4
        ">
          <a :href="isZhLang ? `#/zh-CN/component/search${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/search${docMd === 'react' ? '-react' : ''}`">
            <img src="https://m.hellobike.com/resource/helloyun/13459/FHGw8_search.svg" alt="" class="w-full">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-13
          sm:col-start-4 sm:row-start-7
          lg:col-start-6 lg:row-start-5
          xl:col-start-4 xl:row-start-5
        ">
          <a class=" text-gray-900 dark:text-white" :href="isZhLang ? `#/zh-CN/component/search${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/search${docMd === 'react' ? '-react' : ''}`">
            {{ `${isZhLang ? 'Search (搜索框)' : 'Search'}`}}
          </a>
        </div>
        
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:hidden
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:hidden
          "></div>
        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-14
          sm:col-start-2 sm:row-start-8
          lg:col-start-2 lg:row-start-6
          xl:col-start-6 xl:row-start-4
        ">
          <a :href="isZhLang ? `#/zh-CN/component/swipe${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/swipe${docMd === 'react' ? '-react' : ''}`">
            <img src="https://m.hellobike.com/resource/helloyun/13459/Q2-zR_swipe.svg" alt="" class="w-full">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-15
          sm:col-start-2 sm:row-start-9
          lg:col-start-2 lg:row-start-7
          xl:col-start-6 xl:row-start-5
        ">
          <a class=" text-gray-900 dark:text-white"
            :href="isZhLang ? `#/zh-CN/component/swipe${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/swipe${docMd === 'react' ? '-react' : ''}`">
            {{ `${isZhLang ? 'Swipe (轮播)' : 'Swipe'}`}}
          </a>
        </div>
        
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:hidden
            xl:hidden
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:hidden
            xl:hidden
          "></div>

        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-16
          sm:col-start-4 sm:row-start-8
          lg:col-start-4 lg:row-start-6
          xl:col-start-8 xl:row-start-4
        ">
          <a :href="isZhLang ? `#/zh-CN/component/dialog${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/dialog${docMd === 'react' ? '-react' : ''}`">
            <img class="w-full" src="https://m.hellobike.com/resource/helloyun/13459/Y1Jri_dialog.svg" alt="">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-17
          sm:col-start-4 sm:row-start-9
          lg:col-start-4 lg:row-start-7
          xl:col-start-8 xl:row-start-5
        ">
          <a class=" text-gray-900 dark:text-white" :href="isZhLang ? `#/zh-CN/component/dialog${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/dialog${docMd === 'react' ? '-react' : ''}`">
            {{ `${isZhLang ? 'Dialog (模态框)' : 'Dialog'}`}}  
          </a>
        </div>

        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:hidden
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:hidden
            xl:block
          "></div>

        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-18
          sm:col-start-2 sm:row-start-10
          lg:col-start-6 lg:row-start-6
          xl:col-start-2 xl:row-start-6
        ">
          <a :href="isZhLang ? `#/zh-CN/component/checkbox${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/checkbox${docMd === 'react' ? '-react' : ''}`">
            <img src="https://m.hellobike.com/resource/helloyun/13459/Ob_sY_checkbox.svg" alt="" class="w-full">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-19
          sm:col-start-2 sm:row-start-11
          lg:col-start-6 lg:row-start-7
          xl:col-start-2 xl:row-start-7
        ">
          <a class=" text-gray-900 dark:text-white" :href="isZhLang ? `#/zh-CN/component/checkbox${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/checkbox${docMd === 'react' ? '-react' : ''}`">
            {{ `${isZhLang ? 'Checkbox (复选框)' : 'Checkbox'}`}}
          </a>
        </div>

        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:block
            lg:block
            xl:block
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:hidden
          "></div>
        <div class="bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:hidden
          "></div>

        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-20
          sm:col-start-4 sm:row-start-10
          lg:col-start-2 lg:row-start-8
          xl:col-start-4 xl:row-start-6
        ">
          <a :href="isZhLang ? `#/zh-CN/component/skeleton${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/skeleton${docMd === 'react' ? '-react' : ''}`">
            <img class="w-full" src="https://m.hellobike.com/resource/helloyun/13459/geysn_skeleton.svg" alt="">
          </a>
        </div>
        <div class="h-[90px] bg-white dark:bg-gray-900 px-1 py-2
          col-start-2 row-start-21
          sm:col-start-4 sm:row-start-11
          lg:col-start-2 lg:row-start-9
          xl:col-start-4 xl:row-start-7
        ">
          <a class=" text-gray-900 dark:text-white"
            :href="isZhLang ? `#/zh-CN/component/skeleton${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/skeleton${docMd === 'react' ? '-react' : ''}`">
            {{ `${isZhLang ? 'Skeleton (骨架屏)' : 'Skeleton'}`}}
          </a>
        </div>

        <div class="hidden bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:block
          "></div>
        <div class="hidden bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:block
          "></div>
        <div class="hidden bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:block
          "></div>
        <div class="hidden bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:block
          "></div>

        <div class="bg-white dark:bg-gray-900 p-1
          col-start-2 row-start-20
          sm:col-start-2 sm:row-start-12
          lg:col-start-4 lg:row-start-8
          xl:col-start-6 xl:row-start-6
          flex justify-center items-center
        ">
          <a class="inline-flex text-lg sm:text-xl transition-colors duration-200 focus:ring-2 focus:ring-offset-2 focus:ring-current focus:outline-none rounded-md text-gray-700 hover:text-gray-900 dark:text-gray-500 dark:hover:text-gray-300"
            :href="isZhLang ? `#/zh-CN/component/button${docMd === 'react' ? '-react' : ''}` : `#/en-US/component/button${docMd === 'react' ? '-react' : ''}`">
            {{ t('learnMore') }}
          </a>
        </div>
        <div class="bg-white dark:bg-gray-900 sm:block lg:block xl:block"></div>
        <div class="bg-white dark:bg-gray-900 sm:block lg:block xl:block"></div>
        <div class="bg-white dark:bg-gray-900 sm:block lg:block xl:block"></div>
        <div class="bg-white dark:bg-gray-900 sm:block lg:block xl:block"></div>
        
        <!-- <div class="hidden bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:block
          "></div> -->
        <!-- <div class="hidden bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:block
          "></div> -->
        <!-- <div class="hidden bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:block
          "></div> -->
        <!-- <div class="hidden bg-white dark:bg-gray-900
            sm:hidden
            lg:block
            xl:block
          "></div> -->
      </div>
    </div>
  </div>
</template>
<script lang="ts">
  import { defineComponent } from 'vue';
  import { useI18n } from "vue-i18n";

  export default defineComponent({
    name: 'ComponentsOverview',
    components: {},
    setup() {
      const { t } = useI18n();

      const docMd = localStorage.getItem("docMd");
      
      const isZhLang = localStorage.getItem("language") === "zh-CN";
      
      return { 
        t,
        isZhLang,
        docMd,
      };
    }
  });
</script>
<style src="./index.scss"></style>