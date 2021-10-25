<template>
 <section class="img-select-section">
  <header class="home">
    <h1> {{title}} </h1>
      </header>
      <div class="img-gallery-container-outer">
    <div class="img-gallery-container">
      <div class="img-cont">
      <img :src="image" id="img">
      </div>
      <div class="opacity-change-container">
<input type="radio" id="none" value="None" name="opacity"  v-model="V">
<label for="none" class="input">None</label>

<input type="radio" id="op-val-1" value="0.25" name="opacity"  v-model="V" >
<label for="op-val-1" class="input">0.25</label>

<input type="radio" id="op-val-2" value="0.50" name="opacity"  v-model="V">
<label for="op-val-2" class="input">0.50</label>

<input type="radio" id="op-val-3" value="0.75" name="opacity"  v-model="opValue">
<label for="op-val-3" class="input">0.75</label>
 <p>I am also feeling <em>{{V}}</em> today.</p>
</div>
    </div>
    <div class="img-gallery-container" >
        <ul class="img-gallery">
          <li v-for="image in images" v-bind:key="image" class="list">
            <img @click="updateImg(image.variantImage)" :src="image.variantImage" class="img" id="listImg">
          </li>
        </ul>
    </div>
    </div>

       </section>

  </template>



<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {
      V : "",
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

.flex {
  display: flex;
  flex-direction: column;
}
.home {
  text-align: center;
  font-size: 2rem;
  height: 5%;
  width: 100%;
}
.img-select-section {
  height: 100vh;
  width: 100vw;
}
.img-gallery-container-outer{
display: flex;
flex-direction: row;
height: 95%;
width: 100%;
}


.img-gallery-container {
  flex-direction: column;
  display: flex;
  justify-content: center;
align-content: center;
margin: 2rem;
height: 100%;
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
  
  margin: .2rem;
    height: 50%;
  width: 30%;

}

#listImg {
  cursor: pointer;
}
.img {
  width: 100%;
  height: 100%;
}
.img-cont {

  height: 90%;
  width: 95%;
}
#img {

    width: 100%;
  height: 100%;
}

.opacity-change-container {
    text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 10%;
  width: 100%;
}

.input {
margin: 0 auto;
}


</style>