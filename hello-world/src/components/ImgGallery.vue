<template>

  <section class="img-select-section">
    
    <header class="home">
       <h1> {{title}} </h1>
    </header>

    <div class="img-gallery-container-outer">
      <div class="img-gallery-container">
        <figure class="img-container">
        <img :src="image" id="img" v-bind:style="{ opacity:  opvalue , borderRadius: borderRadius + 'rem',
        border: borderVal, filter: 'blur'+'('+blurValue+'px'+')'}">
      </figure>
    </div>

    <figure class="img-gallery-container" >
        <ul class="img-gallery">
          <li v-for="image in images" v-bind:key="image.variantId" class="list">
            <img @click="updateImg(image.variantImage)" :src="image.variantImage" class="img" id="listImg">
          </li>
        </ul>
    </figure>

    </div>

    <div class="img-editer-container">
     
     <div class="slide-container">
        <input type="range" min="0" max="15" v-model="borderRadius" id="borderRadiusSlider" class="slider">  
         <label for="borderRadiusSlider" class="sliderLabel">border radius</label> 
      </div>

           <div class="slide-container">
        <input type="range" min="0" max="15" v-model="blurValue" id="blurSlider" class="slider">  
         <label for="blurSlider" class="sliderLabel">img blur</label> 
      </div>

    <div class="slide-container">
        <input type="range" min="0.05" max="1" step="0.01" v-model="opvalue" id="opacitySlider" class="slider"> 
        <label for="opacitySlider" class="sliderLabel">slide the slider down to decrease opacity</label>
      </div>
    <div class="border-container">

        <input type="radio" id="border-val-1" value=".5rem solid" v-model="borderVal" class="radio-style">
        <label for="border-val-1" class="radio-style">solid</label>

        <input type="radio" id="border-val-2" value=".3rem dashed" v-model="borderVal" class="radio-style">
        <label for="border-val-2" class="radio-style">dashed</label>

        <input type="radio" id="border-val-3" value="thick double" v-model="borderVal" class="radio-style">
        <label for="border-val-3" class="radio-style">thick double</label>

        <input type="radio" id="border-val-4" value="none" v-model="borderVal" class="radio-style">
        <label for="border-val-4" class="radio-style">no border</label>
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
 
      borderRadius: "0",
      blurValue: "0",
      borderVal: "",
      opvalue : "1",
      image : "https://i.pinimg.com/736x/53/03/86/53038646a6615d11ca2ffb6c47d4878c.jpg",
      title: "Image Changer",

      images: [ {
        variantId: 1,
        variantImage: 'https://i.pinimg.com/originals/10/46/ce/1046ce096a18aeac4074dfc23ee96958.jpg'
      },
       {
        variantId: 2,
        variantImage: 'https://i.pinimg.com/736x/53/03/86/53038646a6615d11ca2ffb6c47d4878c.jpg'
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

    height: 30%;
  width: 45%;

}

#listImg {
  cursor: pointer;
}
.img {
  border-radius: .3rem;
    width: 95%;
     height: 95%;
}
.img-container {
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



.slide-container {
  height: 20%;
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
width: 100%;
}

.slider {
  width: 60%;
}

.sliderLabel {
  margin: .5rem;
}

.border-container {
  width: 100%;
  height: 20%;
    display: flex;
  justify-content: center;
  align-items: center;
}
.radio-style {
  margin: 1rem;
}
</style>