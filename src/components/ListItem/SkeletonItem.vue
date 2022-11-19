<template>
  <li class="skeleton-container">
    <div class="image-container"></div>
    <div class="content-container">
      <p class="name"></p>
      <p class="description"></p>
      <p class="price"></p>
    </div>
  </li>
</template>

<script>
export default {
  name: "SkeletonItem",
  mixins: [],
  components: {},
  props: {},
  data() {
    return {};
  },
  computed: {},
  created() {},
  methods: {},
};
</script>

<style scoped lang="scss">
.skeleton-container {
  display: flex;
  width: 100%;
  margin-block: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
  p {
    margin: 0;
    min-height: 1rem;
  }
}

.image-container {
  position: relative;
  flex-shrink: 0;
  width: 100px;
  height: 100px;
  background-color: lightgray;
  border-radius: 8px;
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

.content-container {
  display: flex;
  width: 100%;
  position: relative;
  margin-left: 1rem;
  flex-direction: column;
  justify-content: space-around;
}

.name {
  width: 13rem;
  background-color: lightgray;
}

.description {
  width: 100%;
  background-color: lightgray;
}

.price {
  width: 7rem;
  background-color: lightgray;
}
</style>
