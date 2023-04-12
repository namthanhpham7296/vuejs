<template>
  <div class="list-user">
    <comp-user
      v-for="user in listUser"
      v-bind:key="user.id"
      v-bind:objectUser="user"
      v-on:deleteUser="deleteUser"
    />
  </div>
</template>

<script>
import CompUser from "./CompUser.vue";
export default {
  name: "comp-list-user",
  props: {
    listUser: {
      type: Array,
      default: []
    }
  },
  data() {
    return {};
  },
  components: {
    CompUser
  },
  methods:{
    deleteUser(data){
      console.log('delete user', data);
      this.$emit('deleteUserEvent', data);
    }
  }
};
</script>

<style>
  .list-user{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  .list-user .user{
    padding: 30px;
    margin-bottom: 30px;
    border: 1px solid #000;
    width: calc(33.333333% - 20px);
  }

</style>
