<template>
  <doc-header></doc-header>

  <div>
    <div class="mx-auto max-w-8xl mb-24">
      <div class="px-4 sm:px-6 lg:px-8">
        <h1 class="mt-24 text-2xl font-extrabold text-gray-800 dark:text-white sm:text-3xl md:max-w-4xl sm:leading-10">
          {{ t("banner.content") }}
          {{ t("banner.desc") }}
        </h1>
      </div>
    </div>

    <ComponentsOverview />
  </div>

  <div class="mx-auto dark:bg-gray-900">
    <div class="px-4 py-16 sm:px-6 lg:px-8">
      <footer class="flex items-center space-x-2 border-t border-gray-800 pt-10">
        <p class="text-xs text-gray-400">A project by</p>
        <div class="text-xs text-gray-400"><a href="/">Quark Design</a></div>
      </footer>
    </div>
  </div>
</template>

<script lang="ts">
  import { defineComponent, onMounted } from "vue";
  import { useI18n } from "vue-i18n";
  import Header from "@/components/Header.vue";
  import ComponentsOverview from "./components/overview/index.vue";


  export default defineComponent({
    name: "Main",
    components: {
      [Header.name]: Header,
      ComponentsOverview,
    },
    setup() {
      const { t } = useI18n();

      onMounted(() => {
        // 默认中文
        if (localStorage.getItem("language") === null) {
          localStorage.setItem("language", "zh-CN");
        }
        // 默认 vue 文档
        if (localStorage.getItem("docMd") === null) {
          localStorage.setItem("docMd", "vue");
        }
      });

      return {
        isZhLang: localStorage.getItem("language") === "zh-CN",
        t,
      };
    },
  });
</script>

<style lang="scss" src="./main.scss"></style>