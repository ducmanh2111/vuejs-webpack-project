<template>
  <div id="app">
    <div class="container">
      <button @click="title = 'Học lập trình tại ZendVN'">Thay doi title tu Component App.vue</button>
      <comp-header 
        :title="title"
        v-on:changeTitleEvent="handleChangeTitle"/>
      <list-products />
      <list-user 
        :listUser='listUser'
        @deleteUserEvent="handleDeleteUser"/>
      <comp-footer 
        :title="title"/>
    </div>
  </div>
</template>

<script>
/*
App (title, listUser[])
  Header (title)
  ListUser (listUser[])
    User (user - object)
    User (user - object)
    User (user - object)
  Footer (title)
*/

import HelloWorld from './components/HelloWorld'
import CompHeader from './components/CompHeader'
import CompFooter from './components/CompFooter'
import ListProducts from './components/ListProducts'
import ListUser from './components/ListUser'

export default {
  name: 'App',
  data() {
    return {
      title: 'Hello VueJS - Header ..',
      listUser: [
        {id: 1, email: 'email1@gmail.com', active: true},
        {id: 101, email: 'email2@gmail.com', active: false},
        {id: 123, email: 'email3@gmail.com', active: true},
        {id: 1234, email: 'email4@gmail.com', active: true}
      ]
    }
  },
  components: {
    HelloWorld,
    CompHeader,
    ListProducts,
    ListUser,
    CompFooter
  },
  methods: {
    handleChangeTitle(data) {
      this.title = data.title
      // console.log("handleChangeTitle được gọi thành công trong App.vue", data);
    },
    handleDeleteUser(data) {
      var indexDelete = -1;

      this.listUser.forEach((u, idx) => {
        if(u.id === data.id) {
          indexDelete = idx;
        }
      });
      // console.log('index cua phan tu can xoa la ' + indexDelete)
      if(indexDelete != -1) {
        this.listUser.splice(indexDelete,1);
      }

      // console.log('handleDelteUser trong App.vue', data);
    }
  }
}
/*
  Props down -> Truyen du lieu tu cha vao con, con không được phép thay đổi trực tiếp 
  Event Up -> Truyền thông điệp ( sự kiện ) thông báo cho component cha biết là nó muốn thay đổi dữ liệu -> Nhiệm vụ của component cha là nhận được thông điệp và tiến hành thay đổi data 
  -> Custom Event Vuejs

  click -> Sự kiện có sẵn trong Vuejs 
  v-on:click="changeTitle"
  'click' -> Tên của sự kiện 
  'changeTitle' -> Hàm xử lí khi sự kiện được kích hoạt ( khi người dùng click )
*/

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  max-width: 1170px;
  margin: 0 auto;
  padding: 0 15px;
  min-height: 3000px;
}
</style>
