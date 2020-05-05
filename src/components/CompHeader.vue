<template>
  <header>
    <h1>{{ title }} <br>
      <button @click="changeTitleHeader($event)">Thay đổi title từ CompHeader.vue</button>
    </h1>
  </header>
</template>

<script>
export default {
  name: 'comp-header',
  props: {
    title: String
  },
  data() {
    return {
    }
  },
  methods: {
    changeTitleHeader(e) {
      // Không được phép thay đổi trực tiếp props từ component cha 
      // -> Truyền sự kiện thông báo ra ngoài 
      // -> Kích hoạt sự kiện 'changeTitleEvent' trong CompHeader.vue
      // -> Khi kích hoạt function bên ngoài App.vue nó sẽ chạy
      // -> Khi function đó dược chạy -> Thay đổi dữ liệu 
      console.log('Trước khi kích hoạt sự kiện changeTitleEvent trong trong CompHeader.vue');
      var data = {
        title: "test -> data truyền thông qua biến event "
      }

      this.$emit('changeTitleEvent', data);
      console.log('Sau khi sự kiện changeTitleEvent trong trong CompHeader.vue xong');
      // console.log(this.title);
    }
  }
}
</script>

<style>

</style>
