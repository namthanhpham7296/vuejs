<template>
  <div class="comp-tabs">
        <div class="tabs-title">
            <span>{{title}}</span>
        </div>
        <div class="tabs-content">
            <slot></slot>
        </div>
  </div>
</template>

<script>
export default {
    name: 'comp-tabs',
    props:{
        title: String
    },
    data(){
        return {

        }
    },
}
</script>

<style>
    .comp-tabs{
        position: relative;
    }
    .tabs-title{

        border: 1px solid #000;
        padding: 15px 30px;
        display: flex;
        justify-content: space-between;
    }

    .tabs-content{
        margin-top: 5px;
        padding: 2px;
        border: 1px solid blue;
    }

    .tabs-header{
        display: flex;
        margin: 0;
        padding: 0;
        list-style-type: none;
    }

    .tabs-header li{
        padding: 8px 15px;
        background-color: #ccc; 
        transition: all 0.3 ease;
    }

    .tabs-header li:hover{
        color: #fff;
        background-color: #333;
    }

    .tab-content{
        padding: 15px;
        border: 1px solid green;
        text-align: left;
    }

</style>