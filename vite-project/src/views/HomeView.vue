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
]
