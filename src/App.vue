<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png" class="mx-auto d-block">
    
    <h1>Mock Up</h1>
    <img src="./assets/comp.png">

    <h2>Requirements</h2>
    <ul>
      <li>Dynamic Header</li>
      <li>Dynamic Subheader</li>
      <li>Dynamic Image</li>
      <li>Dynamic Image</li>
      <li>Large Screens 6 Across</li>
      <li>Small Screens 3 Across</li>
      <li>Xtra Small 1 Across</li>
    </ul>

    <div class="container-fluid">
      <div class="row">
        <template v-for="(petcard, index) in imageDetails">
          <ImageCard :petcard="petcard" :key="index + '-card'"></ImageCard>
        </template>
      </div>
    </div>
  </div>
</template>

<script>
import ImageCard from "./components/ImageCard";
import favorite from "./components/Favorite";

export default {
  name: "App",
  components: {
    ImageCard,
    favorite
  },
  data() {
    return {
      imageDetails: []
    };
  },
  created() {
    this.imageDetails.push({
      id: "11111",
      ad: false,
      mileage: "Forest",
      pricing: {
        our_sale_price: 40000
      },
      attributes: {
        body_style: "Towel"
      },
      price_markup: "$40,000",
      trim_or_body_type_formatted_long: "Towel",
      front_photo: {
        url:
          "https://i.picsum.photos/id/1025/4951/3301.jpg"
      },
      heading: "Cute Dog Thing"
    });

    this.imageDetails.push({
      id: "22222",
      ad: false,
      mileage: "fun fun",
      pricing: {
        our_sale_price: 40000
      },
      attributes: {
        body_style: "Many"
      },
      price_markup: "$40,000",
      trim_or_body_type_formatted_long: "Many",
      front_photo: {
        url:
          "https://i.picsum.photos/id/169/2500/1662.jpg"
      },
      heading: "Dogs Grazing"
    });

    
    for (let i = 0; i < 300; i++) {
      let wieghtedIndex = Math.floor(Math.random() * 8);
      if (wieghtedIndex < 4) {
        this.imageDetails.push(Object.create(this.imageDetails[0]));
      } else if (wieghtedIndex < 8) {
        this.imageDetails.push(Object.create(this.imageDetails[1]));
      } 
    }

  }
};
</script>

<style>
</style>
