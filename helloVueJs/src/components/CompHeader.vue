<template>
  <header>
    <h1>{{ title }}</h1>
    <button v-on:click="changeTitleHeader">Thay đổi title từ CompHeader.vue</button>
  </header>
</template>

<script>
export default {
  name: "comp-header",
  props: {
    title: String
  },
  data() {
    return {};
  },
  methods:{
    changeTitleHeader(e){
      //Không được phép thay đổi trực tiếp props từ component cha
      //-> Truyền sự kiện thông báo ra bên ngoài
      // -> Kích hoạt sự kiện changeTitle ở trong CompHeader
      // -> Khi kích hoạt function bên ngoài App.vue nó sẽ chạy
      // -> Khi function đó được chạy -> Thay đổi dữ liệu
      var data = {
        title: "test -> data truyền thông qua biến event"
      }
      console.log('Trước khi kích hoạt sự kiện changeTitleEvent trong CompHeader.vue');
      this.$emit('changeTitleEvent', data);
      console.log('Sau khi kích hoạt sự kiện changeTitleEvent trong CompHeader.vue');
    }
  }
};
</script>

<style></style>
