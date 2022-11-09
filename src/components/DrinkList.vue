<template>
  <div class="container">
    <h1>음료 목록</h1>
    <tag-menu 
      :menus="menus"
      @onChangeMenu="handleChageMenu"
    ></tag-menu>
    <list-component :list="list"></list-component>
  </div>
</template>

<script>
  import TagMenu from "./Menu/TagMenu.vue";
  import ListComponent from "./List/ListComponent.vue";

  export default {
    name:'DrinkList',
    mixins: [],
    components: {TagMenu, ListComponent},
    props: {
    },
    data(){
      return {
        menus: [ "커피", "티바나", "블렌디드", "기타"],
        totalList: [
          ["a","b","c","d","e","f",],
          ["1","2","3","4","5","6","7","8","9","10",],
        ],
        list: [
        ],
      }
    },
    computed: {
    },
    created () {
      this.list = this.totalList[0];
    },
    methods: {
      handleChageMenu (idx) {
        this.list = [];

        setTimeout(() => {
          this.list = this.totalList[idx];
        }, 500);
      },
    },
  }
</script>

<style scoped>
</style>