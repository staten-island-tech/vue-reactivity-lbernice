<template>
    <div class="shop">
    <ul class="order">
        <li class="stuff">{{order}}</li>  
    </ul>
    <ul class="order">
      <li class="stuff">${{price}}</li>  
    </ul>
</div>
</template>

<script>
export default {
    name: "Cart",
    props: {
        order: String,
        price: Number,
    },
    methods: {

    }
}
</script>

<style>
.shop {
  font-family: 'Times New Roman', Times, serif;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
.order {
  font-weight: bold;
  list-style: none;
}
</style>