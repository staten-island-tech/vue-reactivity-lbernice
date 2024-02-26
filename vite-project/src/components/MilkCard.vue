<template>
  <div class="type">
    <h1 class="milk">{{milk}}</h1>
    <img class="image" :src="img"/>
    <h1 class="price"> ${{price}}</h1>
    <button class="shopcart" @click="$emit('addMilk')">Add To Cart</button>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    milk: String,
    price: Number,
    img: String,
    description: String,
  },
};
</script>

<style>
.milk {
  font-size: 1.8rem;
  margin-bottom: 0rem;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  background-color: white;
  margin-left: 3rem;
}
.price {
  background-color: white;
  font-size: 30px;
  margin-top: 0px;
  margin-bottom: 0px;
  margin-left: 3rem;
}
.image {
  height: 23rem;
  width: auto ;
  object-fit: cover;
  display: block;
  margin-left: 3rem;
  background-color: white;
}
.type {
  display: flex;
  flex-direction: column;
  margin-left: 20px;
  width: 17vw;
}
.shopcart {
  margin-bottom: 20px;
  font-size: 1.6rem;
  margin-left: 3rem;
  border-radius: 10px;
}
</style>