<template>
  <div id="app">
    <div class="container">
      <button v-on:click="title = 'Learning VueJS'">Change Title</button>
      <comp-header
        v-bind:title="title"
        v-on:changeTitleEvent="handleChangeTitle"
      />
      <demo-ref />
      <comp-list-user
        v-on:deleteUserEvent="handleDeleteUser"
        v-bind:listUser="listUser"
      />
      <comp-footer v-bind:title="title" />

      <demo-slot></demo-slot>
    </div>
  </div>
</template>

<script>
import CompHeader from "./components/CompHeader.vue";
import CompFooter from "./components/CompFooter.vue";
import CompListUser from "./components/CompListUser.vue";
import DemoRef from "./components/DemoRef.vue";
import DemoSlot from "./components/DemoSlot.vue";
export default {
  name: "app",
  data() {
    return {
      title: "Hello VueJS",
      listUser: [
        { id: 1, email: "nampt@vtm.co.jp" },
        { id: 2, email: "nganpnt@vtm.co.jp" }
      ]
    };
  },
  components: {
    CompHeader,
    CompFooter,
    CompListUser,
    DemoRef,
    DemoSlot
  },
  methods: {
    handleChangeTitle(data) {
      this.title = data.title;
      console.log(
        "handleChangeTitle được gọi sau khi kích hoạt thành công App.vue " +
          data
      );
    },
    handleDeleteUser(data) {
      var indexDelete = -1;
      this.listUser.forEach((u, idx) => {
        if (u.id == data.id) {
          indexDelete = idx;
        }
      });

      if (indexDelete != -1) {
        this.listUser.splice(indexDelete, 1);
      }

      console.log("handleDeleteUser trong App.vue", data);
    }
  }
};

/* 

props down: Truyền dữ liệu từ thằng cha vào thằng con ->  Thằng con
chỉ được xài thôi. Không được thay đổi.
Event up: Truyền thông thông điệp (sự kiện) thông báo cho component cha biết là nó 
muốn thay đổi dữ liệu -> Nhiệm vụ của component cha nhận được thông điệp
và tiến hành thay đổi -> Custom Even trong VueJS


click -> sự kiện có sẵn trong VueJS
v-on:click="changeTitle"
'click' -> Tên của sự kiện
'changeTitle' -> Hàm xử lý khi sự kiện được kích hoạt khi người dùng click
*/
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  text-align: center;
  max-width: 1174px;
  margin: 0 auto;
  padding: 0 15px;
  min-height: 3000px;
}
</style>
