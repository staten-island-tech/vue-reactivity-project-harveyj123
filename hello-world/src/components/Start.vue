<template>
 <section class="img-select-section">
  <header class="home">
    <h1> {{title}} </h1>
      </header>
      <div class="img-gallery-container-outer">
    <div class="img-gallery-container">
      <div class="img-cont">
      <img :src="image" id="img" v-bind:style="{ opacity:  currentValue/100 , borderRadius: borderRadius + 'rem',
      border: 'borderThickness' + borderVal}">
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
    <div class="img-editer-container">
 <div class="slidecontainer">
        <input
          ref="input"
          v-model="borderRadius"
          type="range"
          :min="0"
          :max="15"
          class="slider"
          @input="onInput"
        >
        
          </div>
            <label for="input">border radius</label>
      <div class="slidecontainer">
        <input
          ref="input"
          v-model="currentValue"
          type="range"
          :min="5"
          :max="100"
          class="slider"
          @input="onInput"
        >
      </div>
 <label for="input">opacity</label>
<div>
<input type="radio" id="border-val-1" value="solid" v-model="borderVal">
<label for="border-val-1">solid</label>
<input type="radio" id="border-val-2" value="dashed" v-model="borderVal">
<label for="border-val-2">dashed</label>
<input type="radio" id="border-val-3" value="thick double" v-model="borderVal">
<label for="border-val-3">thick double</label>
<input type="radio" id="border-val-4" value="ridge" v-model="borderVal">
<label for="border-val-4">ridge</label>
<input type="radio" id="border-val-4" value="none" v-model="borderVal">
<label for="border-val-4">no border</label>
</div>

<input id="border-thickness-val" v-model="borderThickness" placeholder="units in pixels">
<label for="border-thickness-val">input a numerical val for border thickness</label>
    </div>

       </section>

  </template>



<script>
export default {
  name: "Home",
  components: {},
  props: {
    value: {
      type: Number,
      required: true
    },
    min: {
      type: Number,
      required: true
    },
    max: {
      type: Number,
      required: true
    }
  },
  data() {
    return {
      currentValue: this.value,
       borderRadius: "",
       borderVal: "",
      opvalue : "",
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
    },

      onInput() {
      this.$emit('input', parseInt(this.currentValue));
    }
}}
</script>


<style>
  
html,
body,
* {
  background-color: #FBEFE4;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
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
height: 100%;
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
  margin: .3rem;
    height: 30%;
  width: 45%;

}

#listImg {
  cursor: pointer;
}
.img {
  border-radius: .3rem;
    width: 100%;
     height: 100%;
}
.img-cont {
    justify-content: center;
  align-items: center;
display: flex;
  height: 90%;
  width: 95%;
}
#img {

     max-width: 85%;
    height: 85%;
}

.change-img-container {
    text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 5%;
  width: 100%;
}


.slider {
	width: 65%;
	height: .5rem;
	border-radius: 2px;
	background: lightsalmon;
}


.slidecontainer {
  margin: 2rem;
  display: flex;
  justify-content: center;
    flex-direction: column;
  align-items: center;
  width: 100%;
}

.img-editer-container {
  flex-direction: column;
  display: flex;
  justify-content: center;
  align-items: center;
height: 40%;
width: 80%;
}
</style>