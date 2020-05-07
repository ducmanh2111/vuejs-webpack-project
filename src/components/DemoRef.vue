<template>
  <div class="demo-ref">
    <h1>DemoRef</h1>
    <button
      @click="handleClickInputFile"
      class="avatar">Thay đổi avatar</button>
    <input 
      ref="fileInputAvatar"
      type="file"
      style="display: none;">
    <button
      @click="handleClickEmailInput"
      class="email">Thay đổi email</button>
    <input
      ref="emailInput"
      type="email"
      style="display: none;">
  </div>  
</template>

<script>
export default {
  name: 'demo-ref',
  data() {
    return {

    }
  },
  methods: {
    handleClickInputFile(e) {
      this.$refs.fileInputAvatar.click();
      console.log(this);
    },
    handleClickEmailInput(e) {
      console.log(this.$refs.emailInput);
    }
  }
}
</script>

<style>
  .demo-ref {
    margin-top: 100px;
    padding: 100px 30px;
    border: 1px solid #000;
  }

  .avatar {
    color: white;
    border: 2px solid #333;
    padding: 12px 15px;
    background-color: #333;
    transition: all .3s ease;
  }

  .avatar:hover {
    color: #333;
    background-color: #fff;
  }

  .email {
    color: black;
    background-color: mediumseagreen;
    padding: 12px 15px;
  }
</style>
