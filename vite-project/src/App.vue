<template>
  <div id="app">
  <section id="userInput">
    <h1 id="header">Welcome to the Milk Store!</h1>
    <div class="milk-types">
    <Card
      class="type"
      v-for="(milkType, index) in milkTypes"
      @addMilk="addMilk(index)"
      :key="index"
      :milk="milkType.milk"
      :img="milkType.img"
      :price="milkType.price"
    />
  </div>
  </section>

  <section id="shoppingCart">
    <h1>Shopping Cart</h1>
    <Cart
      class="cart"
      v-for="(milkType, index) in order"
      :key="index"
      :order="milkType.milk"
      :price="milkType.price"
    />
    <h2 class = subtotal>Subtotal: ${{ subtotal }}</h2>
    <button class="buttons" @click="remove()">Remove Last Milk</button>
    <button class="buttons" @click="removeAllMilk()">Remove All Milks</button>
    </section>
  </div>
</template>

<script>
import Card from "./components/MilkCard.vue";
import Cart from "./components/MilkCart.vue";
export default {
  milk: "App",
  components: {
    Card,
    Cart,
  },
  data() {
  return {
    subtotal: 0,
    selectedMilk: 0,
    milkTypes: [
    {
    milk: "Skim Milk",
    price: 2.00,
    img: "https://target.scene7.com/is/image/Target/GUEST_6cc723c9-541b-4471-87ec-266271151d35?wid=488&hei=488&fmt=pjpeg",
    },
    {
    milk: "1% Lowfat Milk",
    price: 4.00,
    img: "https://target.scene7.com/is/image/Target/GUEST_4fd1a6cc-ae70-479d-9057-7ab7d142dede",
    },
    {
    milk: "2% Reduced Fat Milk",
    price: 2.00,
    img: "https://i5.walmartimages.com/seo/Great-Value-2-Reduced-Fat-Milk-Half-Gallon-64-fl-oz_e25e894c-0e5d-4ad8-a821-6026b2675f5d.0cf3f1e9c1342c09faf4004eaf7e5499.jpeg",
    },
    {
    milk: "Whole Organic Milk",
    price: 5.00,
    img: "https://californiaranchmarket.com/cdn/shop/products/000586.jpg?v=1616525298",
    },
    {
    milk: "Soy Milk",
    price: 4.00,
    img: "https://target.scene7.com/is/image/Target/GUEST_4cf693f6-b389-4126-a4c1-51ac275f6392?wid=488&hei=488&fmt=pjpeg",
    },
    {
    milk: "Original Almond Milk",
    price: 3.00,
    img: "https://italco.com/wp-content/uploads/2020/01/93ALMMLK.jpg",
    },
    {
    milk: "Silk Protein Milk",
    price: 4.00,
    img: "https://i5.walmartimages.com/seo/Silk-Protein-Original-Pea-Almond-Cashew-Milk-Half-Gallon_dfeeac93-1813-47e2-ad0b-88017d228e46.07bbc0d9880bb40a7fd9a7850dd3c021.jpeg",
    },
    {
    milk: "Oat Milk",
    price: 4.00,
    img: "https://encrypted-tbn1.gstatic.com/shopping?q=tbn:ANd9GcSwNoV5VH4NpDVtFYjXRlDqaL7vp3CywrDn0fjcJ6BAMos-NZzg3gTIbh3uf-m5dqrYYn7veYFkHZKlMUFkPwcUVks4Ps3k8paVSf28lmylV1LIPpxv_XyG",
    },
    {
    milk: "Coconut Milk",
    price: 4.00,
    img: "https://www.kroger.com/product/images/large/front/0002529300122",
    },
    {
    milk: "Rice Milk",
    price: 5.00,
    img: "https://target.scene7.com/is/image/Target/GUEST_3c79e695-ec5e-417c-bc17-b0d1e7d38423?wid=488&hei=488&fmt=pjpeg"
    },
    {
    milk: "Flax Milk",
    price: 5.00,
    img: "https://www.gosupps.com/media/catalog/product/6/1/61ojOiRksTL_2.jpg"
    },
    {
    milk: "Walnut Milk",
    price: 6.00,
    img: "https://cdn.naturamarket.ca/catalog/product/cache/d4b916af0486966841056846415bf5a8/e/l/elmhurst_walnut_us_front.jpg"
    },
    {
    milk: "Hemp Milk",
    price: 6.00,
    img: "https://i5.walmartimages.com/seo/Pacific-Natural-Foods-Hemp-Vanilla-Plant-Based-Milk-32-Fl-Oz-Pack-Of-12_7774c014-d6cc-4d1d-a726-73e902b11a6e.4eb6e77308f4507a6d57dc390726e0df.jpeg"
    },
    {
    milk: "Macadamia Milk",
    price: 6.00,
    img: "https://target.scene7.com/is/image/Target/GUEST_2b37388c-6811-410f-974a-e9ea8af2f531?wid=488&hei=488&fmt=pjpeg"
    },
    {
    milk: "Hazelnut Milk",
    price: 6.00,
    img: "https://elmhurst1925.com/cdn/shop/products/elm_ecomm_us_hazl_32oz_carton_R3_Front_530x@2x.jpg?v=1648146152"
    },
    {
    milk: "Plant-Based (Pea) Milk",
    price: 6.00,
    img: "https://www.ripplefoods.com/img/bottle3.png?ver=113"
    },
    {
    milk: "Pistachio Milk",
    price: 6.00,
    img: "https://m.media-amazon.com/images/S/assets.wholefoodsmarket.com/PIE/product/606b4dd42b575653f14495f0_859918004279-main.jpg"
    },
    {
    milk: "Goat Milk",
    price: 6.00,
    img: "https://i5.walmartimages.com/asr/df1d6c29-246d-417e-be0c-04e380939d95_1.bf59e9a558a82e5041f1e9627cc4d8bb.png"
    },
    {
    milk: "Chocolate Milk",
    price: 6.00,
    img: "https://i5.walmartimages.com/seo/Great-Value-1-Low-Fat-Chocolate-Milk-Half-Gallon-64-fl-oz_60a8e4d7-ea91-4de6-a815-6f302a80be10.0334a38e315e83d004c0d937063d22d1.jpeg"
    },
    {
    milk: "Strawberry Milk",
    price: 6.00,
    img: "https://www.prairiefarms.com/wp-content/uploads/product/23986/072730262556.png"
    },
    {
    milk: "Sesame Milk",
    price: 6.00,
    img: "https://cdn.naturamarket.ca/catalog/product/cache/d4b916af0486966841056846415bf5a8/h/o/hope-and-sesame-original_1_-min.jpg",
    }
  ],
    order: [],
    orderPrice: [],
  };
  },
methods: {
  addMilk(index) {
    this.order.push(this.milkTypes[index]);
    this.orderPrice.push(this.milkTypes[index].price);
    this.subtotal = this.subtotal + this.milkTypes[index].price;
},
  remove() {
  if (this.order.length !== 0) {
    this.subtotal =
    this.subtotal - this.orderPrice[this.orderPrice.length - 1];
    this.order.pop();
    this.orderPrice.pop();
  }
},
  removeAllMilk() {
    this.order = [];
    this.orderPrice = [];
    this.subtotal = 0;
  },
},
};
</script>

<style lang="css">
#header {
  margin-top: 2.3rem;
  text-decoration: underline;
  color: #000000;
  font-family: 'Times New Roman', Times, serif;
  font-size: 2.6rem;
  margin-bottom: 0.7rem;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  display: flex;
  flex-direction: row;
  background-color: #abcfd8;
  color: #000000;
  margin-bottom: 2rem;
}
.img {
  height: 5%;
  width: auto;
}
#userInput {
  width: 57vw;
  height: auto;
}
.subtotal {
  font-size: 1.9rem;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
.milk-types {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  flex-direction: row;
}
#shoppingCart {
  background-color: #cfecf2;
  border: 10px #a3e9e8 solid;
  border-radius: 10px;
  margin-top: 5rem;
  margin-bottom: 3.7rem;
  height: auto;
  color: #000000;
  width: 30vw;
  margin-left: 6rem;
  font-size: 1.5rem;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
.buttons {
  margin-bottom: 1rem;
  font-size: 1.4rem;
  justify-content: center;
  border-radius: 10px;
  width: 35%;
}
section {
  display: flex;
  align-items: center;
  flex-direction: column;
}
</style>