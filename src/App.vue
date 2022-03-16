<template>
  <Header title="Task Tracker" :info="info" active="info-active" inactive="info-inactive"/>
</template>

<script>
import Header from './components/Header.vue'
import logo from './assets/logo.png'



export default {
  name: 'App',
  components:{
    Header
  },
  data(){
    return{
      info:[
        {
        index:0,
        text:'I am info one',
        indicator:true,
        image:''
      },
        {
        index:1,
        text:'I am info two',
        indicator:false,
        image:logo
      },
        {
        index:2,
        text:'I am info three',
        indicator:false,
        image:logo
      }
      ],
      currentIndicatorPosition:0,
      // lastPosition: this.info.length - 1,
      startPosition: 0,
      val:'',
      selected:[],
      checkedNames:[],
      message:[]
    }
  },
  
  // methods:{
  //   moveIndicator(){
  //     let lastPosition = this.info.length - 1;
  //     let nextPosition

  //       if(this.currentIndicatorPosition === lastPosition){
  //       console.log(this.info[this.startPosition],'here');
  //        this.info[this.currentIndicatorPosition].indicator = false;
  //       this.info[this.startPosition].indicator = true
  //       this.currentIndicatorPosition = this.startPosition
  //        console.log(this.info[this.startPosition],'here');       
  //    }else{
  //       this.info[this.currentIndicatorPosition].indicator = false;
  //    nextPosition = this.currentIndicatorPosition + 1;
  //    this.currentIndicatorPosition = nextPosition

  //    console.log(this.currentIndicatorPosition,'current');
  //    console.log(nextPosition,'next')

    
  //         this.info[nextPosition].indicator = true;
   
  //    }
   
    
     
     
    

  //   }
  // },
  // created(){
  //   setInterval(this.moveIndicator,1000);
  // }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.info-active{
  border-left: 1px solid blue;
}
.info-inactive{
  color:gray
}
</style>
