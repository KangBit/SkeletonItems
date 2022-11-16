<template>
  <li class="skeleton-container">
    <div class="image-container">
      <img 
        v-if="item.img.length !== null" 
        :src="item.img"
      />
    </div>
    <div class="content-container">
      <p class="name">{{item.name}}</p>
      <p class="description">{{item.description}}</p>
      <p class="price">{{item.price}}</p>
    </div>
  </li>
</template>

<script>
  export default {
    name:'ListItem',
    mixins: [],
    components: {},
    props: {
      item:{
        type: Object,
        default: () => {
          return {
            name: "",
            description: "",
            price: "",
            img: null,
          }
        }
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
    font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-weight: bold;
  }
}

.image-container{
  position: relative;
  flex-shrink: 0;
  width: 100px;
  height: 100px;
  background-color: lightgray;
  border-radius: 8px;
  img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 8px;
  }
}

.content-container{
  display: flex;
  width: 100%;
  position: relative;
  margin-left: 1rem;
  flex-direction: column;
  justify-content: space-around;
  text-align: left;
}

.price{
  color: palevioletred;
}
</style>