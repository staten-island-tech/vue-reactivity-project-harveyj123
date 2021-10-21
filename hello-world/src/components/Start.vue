<template>
 <section class="img-select-section">
  <header class="home">
    <h1> {{title}} </h1>
      </header>
      <div class="img-gallery-container-outer">
    <div class="img-gallery-container">
      <img :src="image" id="img" >
    </div>
    <div class="img-gallery-container" >
        <ul class="img-gallery">
          <li v-for="image in images" v-bind:key="image" class="list">
            <img @click="updateImg(image.variantImage)" :src="image.variantImage" class="img" id="listImg">
          </li>
        </ul>
    </div>
    </div>
    <v-slider
  dense
  hint="Im a hint"
  max="100"
  min="-100"
></v-slider>
       </section>

  </template>



<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {
      image : "https://www.personality-database.com/profile_images/349339.png",
      title: "Image Changer :3",
      images: [ {
        variantId: 1,
        variantImage: 'https://i.pinimg.com/originals/10/46/ce/1046ce096a18aeac4074dfc23ee96958.jpg'
      },
       {
        variantId: 2,
        variantImage: 'https://www.personality-database.com/profile_images/349339.png'
      },
       {
        variantId: 3,
        variantImage: 'https://www.anime-planet.com/images/characters/34165.jpg?t=1545970466'
      },
       {
        variantId: 4,
        variantImage: 'https://images-na.ssl-images-amazon.com/images/I/71vMGRog+iL.jpg'
      },
       {
        variantId: 5,
        variantImage: 'https://i.redd.it/k4zg1mispls11.jpg'
      },
       {
        variantId: 6,
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

.home {
  font-size: 4rem;
  height: 15%;
  width: 100%;
}
.img-select-section {
  height: 100vh;
  width: 100vw;
}
.img-gallery-container-outer{
  height: 100%;
  width: 100%; 
display: flex;
flex-direction: row;
}

.img-gallery-container {
  display: flex;
  justify-content: center;
align-content: center;
margin: 2rem;
height: 50%;
width: 50%;

}



.img-gallery {
  height: 100%;
  width: 100%;
    display: flex;
    justify-content: center;
    align-content: center;
   flex-wrap: wrap;
  list-style-type: none;
}
.list {
  display: flex;
    justify-content: center;
align-content: center;
  margin: 1rem;
    height: 50%;
  width: 25%;

}

#listImg {
  cursor: pointer;
}
.img {                         

  width: 100%;
  height: auto;
}

#img {

  width: auto;
  height: auto;
}
</style>