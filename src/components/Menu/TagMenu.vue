<template>
  <ul class="tags">
    <li 
      v-for="(title,idx) in menus" :key="idx"
      class="tag-item"
      @click="selectTag(idx)"
      :class="idx === selectedTag ? 'active': ''"
    >{{title}}</li>
  </ul>
</template>

<script>
  export default {
    name:'TagMenu',
    
    props: {
      menus: {
        type: Array,
        default : () => [],
      }
    },

    data(){
      return {
        selectedTag: 0,
      }
    },

    methods: {
      selectTag(idx){
        this.selectedTag = idx;
        this.$emit("onChangeMenu", idx);
      }
    },
  }
</script>

<style scoped lang="scss">
.tags{
  padding: 0;
  width: 100%;
  list-style: none;
  display: flex;
  justify-content: space-evenly;
  .tag-item{
    width: 3rem;
    padding: 0.5rem;
    border-radius: 0.5rem;
    background-color: lightgray;
    cursor: pointer;
  }
  .active{
    background-color: dimgrey;
    color: white;
  }
}

</style>