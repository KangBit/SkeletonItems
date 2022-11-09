<template>
  <div class="container">
    <food-list></food-list>
    <drink-list></drink-list>
  </div>
</template>

<script>
  import FoodList from "../components/FoodList.vue";
  import DrinkList from "../components/DrinkList.vue";

  export default {
    name:'MainHome',
    mixins: [],
    components: {FoodList, DrinkList},
    props: {
    },
    data(){
      return {
        foodCategories: [ "한식", "양식", "중식", "일식"],
        total: [
          ["a","b","c","d","e","f",],
          ["1","2","3","4","5","6","7","8","9","10",],
        ],
        foodList: [
        ],
      }
    },
    computed: {
    },
    created () {
      this.foodList = this.total[0];
    },
    methods: {
      handleChageMenu(idx){
        this.foodList = [];

        setTimeout(() => {
          this.foodList = this.total[idx];
        }, 500);
      },
    },
  }
</script>

<style scoped lang="scss">
.container{
  width: 50vw;
  margin-inline: auto;
}

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

.list-container{
  padding: 0;
  list-style: none;
}
</style>