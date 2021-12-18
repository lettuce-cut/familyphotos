<template>
  <div class="browse">
    <h4>Select as many people as you would like.</h4>
    <h4>Then click "View Family" to see who their parents are.</h4>
    <h4>It's that simple!</h4>
    <ImageList :images="images"/>
  </div>
</template>

<script>
import ImageList from "../components/ImageList.vue"
export default {
  name: 'Browse',
  components: {
    ImageList
  },
  data() {
    return{
    }
  },
  computed: {
    images() {
      console.log(this.$root.$data.images)
      return this.$root.$data.images;
    }
  },
}
</script>

<style scoped>
  ul {
    display:flex;
    justify-content: space-between;
  }
  .pure-menu-link {
    text-decoration: none;
    color:gold;
    font-weight: bolder;
  }
  button {
    border-radius: 25px;
    padding:10px;
    background-color:red;
  }
</style>



