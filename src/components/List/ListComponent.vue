<template>
  <ul class="list-container">
    <skeleton-item
      v-for="(item,idx) in list" :key="idx"
    ></skeleton-item>
  </ul>
</template>

<script>
  import SkeletonItem from "../ListItem/SkeletonItem.vue";

  export default {
    name:'ListComponent',
    mixins: [],
    components: {SkeletonItem},
    props: {
      list:{
        type: Array,
        default: () => [],
      }
    },
    data(){
      return {
      }
    },
    computed: {
    },
    created () {
    },
    methods: {
    },
  }
</script>

<style scoped>
</style>