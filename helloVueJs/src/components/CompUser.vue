<template>
  <div class="user">
        <p>{{ objectUser.email }}</p>
        <button  v-on:click="handleDelete" class="delete">Delete</button>
  </div>
</template>

<script>
export default {
    name: 'comp-user',
    props:{
      objectUser:{
        type: Object,
        default: null
      }
    },
    data(){
        return {

        }
    },
    methods:{
      handleDelete(e){
        var data = {
            id: this.objectUser.id

        };
        console.log('handleDelete trong User.vue')
        this.$emit("deleteUser", data);
      }
    }
}
</script>

<style>
  .user{
    position: relative;
  }

  .user .delete{
    position: absolute;
    top: 0;
    right: 0;
  }
</style>