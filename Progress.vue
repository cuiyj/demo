<template>
    <div class="progress">
        <div class="progress_bar">
            <div class="progress_bar_outer"
                 :style="{height:strokeWidth+'px'}">
                <div class="progress_bar_inner" :style="barStyle"></div>
            </div>
        </div>
        <div class="progress_text"
             :style="{fontSize:progressTextSize+'px'}">
            {{percentage}}%
        </div>
    </div>
</template>
<script>
export default {
  props: {
    strokeWidth: {
      type: Number,
      default: 6
    },
    percentage: {
      type: Number,
      required: true,
      default: 0,
      validator: val => val >= 0 && val <= 100
    },
    status:{
        type:String
    }
  },
  computed: {
    progressTextSize() {
      return 12 + this.strokeWidth * 0.4;
    },
    stroke(){
        let color;
        switch(this.status){
            case 'success':
               color ='#13ce66';
               break;
            case 'exeption':
               color ='#ff4949';
               break;
            default:
               color ='#20a0ff';
               break;
        }
        return color;
    },
    barStyle(){
        return {
            width:this.percentage+'%',
            backgroundColor:this.stroke
        }
    }
  }
};
</script>
<style>
.progress {
  /* background-color: rgb(88, 79, 61); */
  /* height: 100px; */
  /* width: 800px; */
}
.progress_bar {
  width: 100%;
  /* height: 50px; */
  display: inline-block;
  box-sizing: border-box;
  /* background-color: sandybrown; */
  padding-right: 50px;
  margin-right: -40px;
}
.progress_bar_outer {
  border-radius: 100px;
  /* width: 200px; */
  background-color: rgba(168, 167, 167, 0.336);
}
.progress_bar_inner {
  /* width: 60px; */
  height: 100%;
  transition: width 0.6s ease;
  border-radius: 100px;
  /* background-color: rgb(96, 160, 212); */
}
.progress_text {
  display: inline-block;
  /* background-color: slateblue; */
  /* margin-left: 12px; */
  /* width: 50px; */
  /* height: 50px; */
}
</style>

