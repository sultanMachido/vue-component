<template>
  <h1>{{ title }}</h1>
  <div
    :key="inf.index"
    v-for="inf in content"
    :class="{ active: inf.indicator, inactive: !inf.indicator }"
    class="info"
  >
    <div>
      <p>{{ inf.text }}</p>
    </div>
     
  </div>
  <div >
        <img v-if="imgSrc" :src="imgSrc" alt="illustration">
    </div>
    
</template>


<script>
export default {
  name: "Header",
  props: {
    title: String,
    info: Array,
    active: String,
    inactive: String,
  },
  data() {
    return {
      content: [...this.info],
      currentIndicatorPosition: 0,
      // lastPosition: this.info.length - 1,
      startPosition: 0,
      imgSrc:''
    };
  },
  methods: {
    moveIndicator() {
      let lastPosition = this.content.length - 1;
      let nextPosition;
      //   console.log('here2')
      //    console.log(this.props.info,'props')
      if (this.currentIndicatorPosition === lastPosition) {
        console.log(this.content[this.startPosition], "here");
        this.content[this.currentIndicatorPosition].indicator = false;
        this.content[this.startPosition].indicator = true;
        this.currentIndicatorPosition = this.startPosition;
        console.log(this.content[this.startPosition], "here");
      } else {
        this.content[this.currentIndicatorPosition].indicator = false;
        nextPosition = this.currentIndicatorPosition + 1;
        this.currentIndicatorPosition = nextPosition;

        console.log(this.currentIndicatorPosition, "current");
        console.log(nextPosition, "next");

        this.content[nextPosition].indicator = true;
      }

     this.imgSrc = this.content[this.currentIndicatorPosition].image || '';
    },
  },
  created() {
    setInterval(this.moveIndicator, 1000);
    // console.log(this.info,'info');
  },
};
</script>

<style>
.active {
  border-left: 1px solid blue;
}
.inactive {
  color: gray;
}
.info {
  height: 30px;
  width: 500px;
  display: flex
}
</style>