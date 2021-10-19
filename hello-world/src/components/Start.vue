<template>
 <section class="img-select-section">
  <header class="home">
    <h1> {{title}} </h1>
      </header>
      <div class="img-gallery-container-outer">
    <div class="img-gallery-container">
      <div class="img-gallery-container-inner">
      <img :src="image" class="img" >
      </div>
    </div>
    <div class="img-gallery-container">
        <ul class="img-gallery">
          <li @="image in images" v-bind:key="image" class="list">
            <img :src="image.variantImage" class="img">
          </li>
        </ul>
    </div>
    </div>
       </section>

  </template>

    //click

<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {
      image : "https://www.personality-database.com/profile_images/349339.png",
      title: ":3 asdasd",
      images: [ {
        variantId: 1,
        variantImage: 'https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg'
      },
       {
        variantId: 2,
        variantImage: 'https://www.personality-database.com/profile_images/349339.png'
      },
       {
        variantId: 3,
        variantImage: 'https://www.personality-database.com/profile_images/349339.png'
      },
       {
        variantId: 3,
        variantImage: 'https://www.personality-database.com/profile_images/349339.png'
      },
       {
        variantId: 4,
        variantImage: 'https://www.personality-database.com/profile_images/349339.png'
      },
       {
        variantId: 5,
        variantImage: 'https://www.anime-planet.com/images/characters/34170.jpg?t=1529534556'
      }, ]
    };
  },
  methods: {
    updateImg(variantImage) {
      this.image = variantImage
    }
}}
</script>


<style>
  
html,
body,
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.img-select-section {
  height: 100vh;
  width: 100vw;
}
.img-gallery-container-outer{
display: flex;
flex-direction: row;
}
.img-gallery-container-inner {
  height: 80%;
  width: 80%;
}
.img-gallery-container {
  display: flex;
  justify-content: center;
align-content: center;
margin: 2rem;
height: 60%;
width: 50%;
}
.img-gallery {
    display: flex;
    justify-content: center;
    align-content: center;
   flex-wrap: wrap;
  list-style-type: none;
}
.list {
  padding: .5rem;
  margin: .5rem;
}
.img {
  width: 100%;
  height: auto;
}
</style>