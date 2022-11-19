<template>
  <div>
    <h2>{{ title }}</h2>
    <tag-menu
      :menus="menus"
      :disable="isLoading"
      @onChangeMenu="handleChageMenu"
    ></tag-menu>

    <ul v-show="isShowSkeletonItems" class="list-container">
      <skeleton-item v-for="idx in skeletonSize" :key="idx"></skeleton-item>
    </ul>
    <ul v-show="isShowNoItem" class="list-container">
      <h1>NO-ITEM</h1>
    </ul>
    <ul v-show="isShowItems" class="list-container">
      <list-item
        v-for="(item, idx) in list"
        :key="idx"
        :item="item"
      ></list-item>
    </ul>
  </div>
</template>

<script>
import TagMenu from "../Menu/TagMenu.vue";
import SkeletonItem from "../ListItem/SkeletonItem.vue";
import ListItem from "../ListItem/ListItem.vue";

export default {
  name: "ListComponent",
  mixins: [],
  components: {
    TagMenu,
    SkeletonItem,
    ListItem,
  },
  props: {
    title: {
      type: String,
      default: "",
    },
    menus: {
      type: Array,
      default: () => [],
    },
    totalList: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      isLoading: false,
      skeletonSize: 5,
      list: null,
    };
  },
  computed: {
    isShowSkeletonItems() {
      return this.list === null;
    },
    isShowNoItem() {
      return Array.isArray(this.list) && this.list.length === 0;
    },
    isShowItems() {
      return !this.isShowSkeletonItems && !this.isShowNoItem;
    },
  },
  watch: {
    list(curr, prev) {
      if (!Array.isArray(prev)) {
        this.skeletonSize = 5;
        return;
      }

      if (prev.length === 0) {
        this.skeletonSize = 1;
      } else {
        this.skeletonSize = prev.length;
      }
    },
  },
  created() {
    this.isLoading = true;
    this.list = this.totalList[0];
    this.isLoading = false;
  },
  methods: {
    handleChageMenu(idx) {
      this.isLoading = true;
      this.list = null;

      setTimeout(() => {
        this.list = this.totalList[idx];
        this.isLoading = false;
      }, 3000);
    },
  },
};
</script>

<style scoped>
.list-container {
  padding: 0;
  list-style: none;
}
</style>
