<template>
  <li class="skeleton-container">
    <div class="image-container"></div>
    <div class="content-container">
      <p class="title"></p>
      <p class="sub-title"></p>
      <p class="date"></p>
    </div>
  </li>
</template>

<script>
  export default {
    name:'SkeletonItem',
    mixins: [],
    components: {},
    props: {
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

<style scoped lang="scss">
.skeleton-container{
  display: flex;
  width: 100%;
  margin-block: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
  p{
    margin: 0;
    min-height: 1rem;
  }
}

.image-container{
  position: relative;
  flex-shrink: 0;
  width: 80px;
  height: 80px;
  background-color: lightgray;
  border-radius: 8px;
}

.content-container{
  display: flex;
  width: 100%;
  position: relative;
  margin-left: 1rem;
  flex-direction: column;
  justify-content: space-around;
}

.title{
  width: 13rem;
  background-color: lightgray;
}

.sub-title{
  width: 100%;
  background-color: lightgray;
}

.date{
  width: 7rem;
  background-color: lightgray;
}
</style>