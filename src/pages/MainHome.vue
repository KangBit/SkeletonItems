<template>
  <div class="container">
    <list-component :title="'음식 목록'" :menus="foodMenus" :totalList="foodList"></list-component>
    <list-component :title="'음료 목록'" :menus="drinkMenus" :totalList="drinkList"></list-component>
  </div>
</template>

<script>
  import ListComponent from "../components/List/ListComponent.vue"

  export default {
    name:"MainHome",
    mixins: [],
    components: {ListComponent},
    props: {
    },
    data(){
      return {
        foodMenus: ["한식", "양식", "중식", "일식"],
        drinkMenus: ["차", "커피", "블렌디드", "기타"],

        foodList: [
          [
            {name:"비빔밥",description:"맛있게 비벼먹어요",price:"5,000", img:require("@/assets/imgs/food/kfood01.jpg")},
            {name:"돌솥비빔밥",description:"뜨겁게 비벼먹어요",price:"5,500", img:require("@/assets/imgs/food/kfood02.jpg")},
            {name:"김밥",description:"밥을 김으로 감싸 둥글게 만 뒤 잘라낸 음식",price:"5,700", img:require("@/assets/imgs/food/kfood03.jpg")},
            {name:"떡볶이",description:"떡과 부재료를 양념에 볶거나 끓여서 먹는 음식",price:"6,000", img:require("@/assets/imgs/food/kfood04.jpg")},
            {name:"육회",description:"가늘게 채를 친 고기를 전혀 익히지 않고 설탕, 소금, 간장, 마늘, 참기름 등으로 만든 양념에 버무려 먹는 음식",price:"9,000", img:require("@/assets/imgs/food/kfood05.jpg")},
          ],
          [
            {name:"샐러드",description:"연어가 듬뿍 들어간 연어샐러드",price:"9,800", img:require("@/assets/imgs/food/afood01.jpg")},
            {name:"스테이크",description:"소고기로 만든 비프 스테이크",price:"17,200", img:require("@/assets/imgs/food/afood02.jpg")},
            {name:"햄버거",description:"패티를 구운 후 다양한 부재료와 함께 빵 사이에 끼워 먹는 음식",price:"8,000", img:require("@/assets/imgs/food/afood03.jpg")},
            {name:"피자",description:" 밀가루로 만든 얇고 납작한 반죽에 토마토 소스와 치즈 등 토핑을 얹어서 구워 먹는 요리",price:"8,000", img:require("@/assets/imgs/food/afood04.jpg")},
            {name:"로제파스타",description:"로제소스로 만든 파스타",price:"8,600", img:require("@/assets/imgs/food/afood05.jpg")},
            {name:"까르보나라",description:"관찰레를 볶아 기름을 낸 뒤에 달걀 노른자에 치즈와 후추를 섞은 소스를 면과 함께 버무린 파스타",price:"9,000", img:require("@/assets/imgs/food/afood06.jpg")},
            {name:"미트파이",description:"고기를 주재료로 사용한 파이.",price:"9,700", img:require("@/assets/imgs/food/afood07.jpg")},
            {name:"핫도그",description:"기다란 모양의 소시지, 또는 그것을 핫도그 번에 끼운 음식",price:"7,000", img:require("@/assets/imgs/food/afood08.jpg")},
          ],
        ],
        drinkList: [
          [
            {name:"",description:"",price:"", img:require("@/assets/imgs/drink/tea01.jpg")},
            {name:"",description:"",price:"", img:require("@/assets/imgs/drink/tea02.jpg")},
            {name:"",description:"",price:"", img:require("@/assets/imgs/drink/tea03.jpg")},
          //   {name:"",description:"",price:"", img:""},
          //   {name:"",description:"",price:"", img:""},
          //   {name:"",description:"",price:"", img:""},
          //   {name:"",description:"",price:"", img:""},
          //   {name:"",description:"",price:"", img:""},
          //   {name:"",description:"",price:"", img:""},
          //   {name:"",description:"",price:"", img:""},
          ],
          [
            {name:"커피1",description:"",price:"", img:require("@/assets/imgs/drink/coffee01.jpg")},
            {name:"커피2",description:"",price:"", img:require("@/assets/imgs/drink/coffee01.jpg")},
            {name:"커피3",description:"",price:"", img:require("@/assets/imgs/drink/coffee01.jpg")},
            {name:"커피4",description:"",price:"", img:require("@/assets/imgs/drink/coffee01.jpg")},
            {name:"커피5",description:"",price:"", img:require("@/assets/imgs/drink/coffee01.jpg")},
          ],
        ],
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
.container{
  width: 50vw;
  margin-inline: auto;
}
</style>