<template>
  <div>
<DestCard v-for="destination in destinations" 
:key="destination.name" :Destination="destination"/>
  </div>
</template>

<script setup>
import DestCard from '@/components/icons/DestCard.vue';
const destinations = [
  {
    name: "Skim Milk",
    price: 2.19,
    img: "https://target.scene7.com/is/image/Target/GUEST_6cc723c9-541b-4471-87ec-266271151d35?wid=488&hei=488&fmt=pjpeg",
  },
  {
    name: "1% Lowfat Milk",
    price: 3.49,
    img: "https://target.scene7.com/is/image/Target/GUEST_4fd1a6cc-ae70-479d-9057-7ab7d142dede",
  },
  {
    name: "2% Reduced Fat Milk",
    price: 1.77,
    img: "https://i5.walmartimages.com/seo/Great-Value-2-Reduced-Fat-Milk-Half-Gallon-64-fl-oz_e25e894c-0e5d-4ad8-a821-6026b2675f5d.0cf3f1e9c1342c09faf4004eaf7e5499.jpeg",
  },
  {
    name: "Whole Organic Milk",
    price: 4.89,
    img: "https://californiaranchmarket.com/cdn/shop/products/000586.jpg?v=1616525298",
  },
  {
    name: "Soy Milk",
    price: 3.99,
    img: "https://target.scene7.com/is/image/Target/GUEST_4cf693f6-b389-4126-a4c1-51ac275f6392?wid=488&hei=488&fmt=pjpeg",
  },
  {
    name: "Coconut Milk",
    price: 4.29,
    img: "https://www.kroger.com/product/images/large/front/0002529300122",
  },
  {
    name: "Unsweetened Coconut Milk",
    price: 4.29,
    img: "https://target.scene7.com/is/image/Target/GUEST_013bec28-c3c9-4f9a-bea7-a8b43d9d2d74?wid=488&hei=488&fmt=pjpeg",
  },
  {
    name: "Unsweetened Almond Milk",
    price: 2.39,
    img: "https://target.scene7.com/is/image/Target/GUEST_69f9584f-8f6d-4af9-a678-8ab752f691f6?wid=488&hei=488&fmt=pjpeg",
  },
  {
    name: "Original Almond Milk",
    price: 2.99,
    img: "https://italco.com/wp-content/uploads/2020/01/93ALMMLK.jpg",
  },
  {
    name: "Silk Protein Milk",
    price: 3.98,
    img: "https://i5.walmartimages.com/seo/Silk-Protein-Original-Pea-Almond-Cashew-Milk-Half-Gallon_dfeeac93-1813-47e2-ad0b-88017d228e46.07bbc0d9880bb40a7fd9a7850dd3c021.jpeg",
  },
  {
    name: "Oat Milk",
    price: 4.29,
    img: "https://encrypted-tbn1.gstatic.com/shopping?q=tbn:ANd9GcSwNoV5VH4NpDVtFYjXRlDqaL7vp3CywrDn0fjcJ6BAMos-NZzg3gTIbh3uf-m5dqrYYn7veYFkHZKlMUFkPwcUVks4Ps3k8paVSf28lmylV1LIPpxv_XyG",
  },
  {
    name: "Rice Milk",
    price: 4.99,
    img: "https://target.scene7.com/is/image/Target/GUEST_3c79e695-ec5e-417c-bc17-b0d1e7d38423?wid=488&hei=488&fmt=pjpeg"
  },
  {
    name: "Flax Milk",
    price: 4.99,
    img: "https://www.gosupps.com/media/catalog/product/6/1/61ojOiRksTL_2.jpg"
  },
  {
    name: "Walnut Milk",
    price: 5.99,
    img: "https://cdn.naturamarket.ca/catalog/product/cache/d4b916af0486966841056846415bf5a8/e/l/elmhurst_walnut_us_front.jpg"
  },
  {
    name: "Hemp Milk",
    price: 5.80,
    img: "https://i5.walmartimages.com/seo/Pacific-Natural-Foods-Hemp-Vanilla-Plant-Based-Milk-32-Fl-Oz-Pack-Of-12_7774c014-d6cc-4d1d-a726-73e902b11a6e.4eb6e77308f4507a6d57dc390726e0df.jpeg"
  },
  {
    name: "Macadamia Milk",
    price: 3.69,
    img: "https://target.scene7.com/is/image/Target/GUEST_2b37388c-6811-410f-974a-e9ea8af2f531?wid=488&hei=488&fmt=pjpeg"
  },
  {
    name: "Hazelnut Milk",
    price: 6.29,
    img: "https://elmhurst1925.com/cdn/shop/products/elm_ecomm_us_hazl_32oz_carton_R3_Front_530x@2x.jpg?v=1648146152"
  },
  {
    name: "Plant-Based(Pea) Milk",
    price: 5.29,
    img: "https://www.ripplefoods.com/img/bottle3.png?ver=113"
  },
  {
    name: "Pistachio Milk",
    price: 9.59,
    img: "https://m.media-amazon.com/images/S/assets.wholefoodsmarket.com/PIE/product/606b4dd42b575653f14495f0_859918004279-main.jpg"
  },
  {
    name: "Goat Milk",
    price: 5.23,
    img: "https://i5.walmartimages.com/asr/df1d6c29-246d-417e-be0c-04e380939d95_1.bf59e9a558a82e5041f1e9627cc4d8bb.png"
  },
  {
    name: "Chocolate Milk",
    price: 1.80,
    img: "https://i5.walmartimages.com/seo/Great-Value-1-Low-Fat-Chocolate-Milk-Half-Gallon-64-fl-oz_60a8e4d7-ea91-4de6-a815-6f302a80be10.0334a38e315e83d004c0d937063d22d1.jpeg"
  },
  {
    name: "Strawberry Milk",
    price: 2.57,
    img: "https://www.prairiefarms.com/wp-content/uploads/product/23986/072730262556.png"
  },
]

</script>

<style scoped>

</style>