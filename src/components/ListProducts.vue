<template>
  <div class="list-products">
    <ul>
      <li v-for="item in listProducts" v-bind:key="item.id"> {{ item.color }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'list-products',
  data() {
    return {
      listProducts: [
        {
          id: 1,
          color: "Vàng"
        },
        {
          id: 2,
          color: "Xanh"
        }
      ]
    }
  }
}
</script>

<style>

</style>
