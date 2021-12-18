<template>
<div class="wrapper">
  <div class="images">
    <div class="image" v-for="image in images" :key="image.id">
        <img :src="'images/'+image.image">
        <button a @click="addToCart(image)" href="#">{{image.name}}</button>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'ImageList',
  props: {
    images: Array
  },
  methods:{
    addToCart(image) {
      this.$root.$data.cart.push(image)
    },
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}


.images {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.image {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.image img {
  border: 3px solid goldenrod;
  height: 250px;
  width: 200px;
  object-fit: cover;
  border-radius: 25px;

}


h1 {
  font-size: 16px;
  background-color: goldenrod;
  padding:0;
  margin: 0;
  border-radius: 25px;
  color: black;
}

button {
  height: 40px;
  width: 100px;
  background: goldenrod;
  color: black;
  border-radius: 10px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-weight: bold;
  
}

.auto {
  margin-left: auto;
}
</style>