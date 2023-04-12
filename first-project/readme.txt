1. Cài đặt vuejs 
<script src="https://cdn.jsdelivr.net/npm/vue@2.7.8"></script>
2. Vue Instance có thể gọi là một thực thể vue hoặc một đối lượng Vue 
Every Vue application starts by creating a new Vue instance with the Vue function:
Khởi tạo một đối tượng vue và truyền cho nó một object để khai báo những thông tin liên quan
Ví dụ để báo cho vue nào đó biết nó quản lý thành phần nào thì phải trỏ đến thành phần đó trong qua element 
được viết tắt bởi "el"
var vm = new Vue({
  // options
})
Trong vue instance có hai phần data và methods 
var vueInstance = new Vue({
  el: "#app",
  data:{
    //EX
    title: 'Hello World'
  },
  methods:{
    //EX
    say: function(text){
        return 'Hello' + text;
    }
  }
});
3 Ràng buộc dữ liệu một chiều với Data Binding 
và sử dụng biểu thức Javascript Expression


4. Listening to Events, Method Event handles, 
Methods in inline Handlers Xử lý sự kiện thông qua v-on:click=""


. Event Modifiers
<!-- the click event's propagation will be stopped -->
<a v-on:click.stop="doThis"></a>

<!-- the submit event will no longer reload the page -->
<form v-on:submit.prevent="onSubmit"></form>

<!-- modifiers can be chained -->
<a v-on:click.stop.prevent="doThat"></a>

<!-- just the modifier -->
<form v-on:submit.prevent></form>

<!-- use capture mode when adding the event listener -->
<!-- i.e. an event targeting an inner element is handled here before being handled by that element -->
<div v-on:click.capture="doThis">...</div>

<!-- only trigger handler if event.target is the element itself -->
<!-- i.e. not from a child element -->
<div v-on:click.self="doThat">...</div>
6. Computed
7. Ràng buộc dữ liệu hai chiều với binding html class và binding style class
8. Conditions: Render Template dùng biểu thức điều kiện
9. List Rendering
10. Render Html thông qua v-html=""
11 Vue CLI (Command Line Interface)