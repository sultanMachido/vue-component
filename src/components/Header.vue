<template>
   <h1>{{title}}</h1> 
   <div :key="inf.index" v-for="inf in info" :class="{active:inf.indicator,inactive:!inf.indicator}" class="info">
       {{inf.text}}
   </div>
</template>


<script>
export default {
    name:'Header',
    props:{
        title:String,
        info: Array,
        active:String,
        inactive:String
    }
}
</script>

<style>
 .active{
  border-left: 1px solid blue;
}
.inactive{
  color:gray
}
.info{
    height:30px;
    width:100px
}
</style>