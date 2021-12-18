<template>
<div class="cart">
  <div class="cart-item" v-for="image in cart" :key="image.id">
    <div class="item">
      <div class="chosen">
        <img :src="'./images/'+image.image">
        <h1>{{image.name}}</h1>
      </div>
      <h3>Child of</h3>
      <div class="chosen-mom">
        <img :src="'./images/'+imageMom(image)">
        <!-- <img src='"/images/' + {{imageMom(image)}}> -->
        <h1>{{image.mom}}</h1>
      </div>
      <div class="chosen-dad">
        <img :src="'./images/'+imageDad(image)">
        <h1>{{image.dad}}</h1>
      </div>
    </div>
    <button a @click="removeFromCart(image)" href="#">Remove Person from Viewing</button>
  </div>
</div>
</template>

<script>
export default {
  name: 'ViewList',
  props: {
    cart: Array
  },
  methods: {
    imageMom(image) {
      for (let i = 0; i < this.$root.$data.images.length; i++) {
        if (image.mom == this.$root.$data.images[i].name) {
          return this.$root.$data.images[i].image
        }
      }
    },
    imageDad(image) {
      for (let i = 0; i < this.$root.$data.images.length; i++) {
        if (image.dad == this.$root.$data.images[i].name) {
          return this.$root.$data.images[i].image
        }
      }
    },
    removeFromCart(image) {
      const index = this.$root.$data.cart.indexOf(image);
      if (index > -1) {
        this.$root.$data.cart.splice(index, 1)
      }
    }
  }
}
</script>

<style scoped>

img {
  height: 20vh;
  border-radius: 100px;
  padding: 5px;
  border: 2px solid goldenrod;
}

button {
  height: 35px;
  margin: 20px;
  padding: 2px;

  background: goldenrod;
  color: black;
  border-radius: 10px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-weight: bold;
}

.cart-item {
  /* background-color: green; */
  height: 20vh;
  padding: 60px;
  margin: 25px;
  width: 90vw;
  border: 2px solid goldenrod;
}
.item {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  flex-direction: row;
}

h3 {
  display: flex;
  align-items: center;
}

h1 {
  font-size: 16px;
  padding:0;
  margin: 0;
  color: black;
}

.below {
  display: flex;
  /* border: 2px black solid; */
  margin: 5px;
}

.cart {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

</style>