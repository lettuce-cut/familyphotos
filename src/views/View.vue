<template>
<div>
    <h1>Viewing Photos</h1>
    <ViewList :cart="cart"/>
</div>
</template>

<script>
import ViewList from "../components/ViewList.vue"
export default {
  name: 'View',
  components: {
    ViewList
  },
  computed: {
    cart() {
      return this.$root.$data.cart
    }
  },
}
</script>
