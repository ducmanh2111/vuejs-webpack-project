<template>
  <div class="comp-tabs">
    <div class="tabs-title">
      <span>{{ title }}</span>
      <ion-icon name="heart"></ion-icon>
    </div>
    <div class="tabs-content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'comp-tabs',
  props: {
    title: String
  },
  data() {
    return {

    }
  }
}
</script>

<style>
  .tabs-title {
    padding: 15px 30px;
    display: flex;
    justify-content: space-between;
    border: 2px solid #000;
  }

  .tabs-header {
    margin: 0;
    padding: 0;
    display: flex;
    list-style-type: none;
  }

  .tabs-header li {
    padding: 8px 15px;
    background-color: #ccc;
    transition: ease .3s all;
  }

  .tabs-header li:hover {
    color: #fff;
    background-color: #333;
  }

  .tabs-content {
    margin-top: 2px;
    padding: 2px;
    border: 2px solid blue;
  }

  .tabs-content {
    padding: 15px;
    border: 2px solid green;
    text-align: left;
  }

  .active {
    background-color: mediumseagreen !important;
  }
</style>
