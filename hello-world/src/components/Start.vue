<template>
  <header class="home">
    <h1> {{title}} </h1>
    <div >
        <ul class="img-gallery">
          <li v-for="image in images" v-bind:key="image">
            <img :src="image">
          </li>
        </ul>
    </div>
  </header>
  </template>

    

<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {
      image : "https://www.personality-database.com/profile_images/349339.png",
      title: ":3 asdasd",
      images: ["https://www.personality-database.com/profile_images/349339.png", "https://www.personality-database.com/profile_images/349339.png","https://www.personality-database.com/profile_images/349339.png"]
    };
  },
  methods: {

  },
};
</script>


<style>
.img-gallery {
  list-style-type: none;
}
</style>

