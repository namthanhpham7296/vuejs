<template>
  <div class="demo-ref">
    <h1>Demo Ref</h1>
    <button v-on:click="handleClickInputFile" class="avatar">Upload File</button>
    <input ref="fileInputAvatar" type="file" style="display: none;">
  </div>
</template>

<script>
export default {
    name: 'demo-ref',
   
    data(){
        return {

        }
    },
    methods:{
     handleClickInputFile(e){
        this.$refs.fileInputAvatar.click();
     }
     
    }
}
</script>

<style>
  .avatar{
    color: #fff;
    border: 2px solid #000;
    padding: 12px 15px;
    background-color: #333;
    transition: all .3 ease;
  }

  .avatar:hover{
    color: #333;
    background-color: #fff;
  }
</style>