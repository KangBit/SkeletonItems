<template>
  <div>
    <h2>{{title}}</h2>
    <tag-menu 
      :menus="menus"
      :disable="isLoading"
      @onChangeMenu="handleChageMenu"
    ></tag-menu>

    <!-- <ul class="list-container">
      <skeleton-item
        v-for="idx in size" :key="idx"
      ></skeleton-item>
    </ul> -->

    <ul v-if="list.length === 0" class="list-container">
      <skeleton-item
        v-for="idx in 5" :key="idx"
      ></skeleton-item>
    </ul>
    <ul v-else class="list-container">
      <list-item
        v-for="(item,idx) in list" :key="idx"
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
    name:'ListComponent',
    mixins: [],
    components: {
      TagMenu,
      SkeletonItem,
      ListItem,
    },
    props: {
      title: {
        type: String,
        default: ""
      },
      menus: {
        type: Array,
        default: () => [],
      },
      totalList:{
        type: Array,
        default: () => [],
      },
    },
    data(){
      return {
        isLoading: false,
        list: [],
        size: 5,
      }
    },
    computed: {
    },
    created () {
      this.isLoading = true;
      this.list = this.totalList[0];
      this.isLoading = false;
    },
    methods: {
      handleChageMenu (idx) {
        this.isLoading = true;
        this.list = [];
        this.size = 0

        setTimeout(() => {
          this.size = 8
          this.list = this.totalList[idx];
          this.isLoading = false;
        }, 500);
      },
    },
  }
</script>

<style scoped>
.list-container{
  padding: 0;
  list-style: none;
}
</style>