<template>
    <!-- <div>{{msg}}</div> -->
    <div>
        <!-- <h2>外显</h2> -->
        <d-progress />
        <d-progress percentage='50'/>
        <d-progress percentage='100'  status="success"/>
        <d-progress percentage='70' status="exeption"/>

        <br>
        <!-- <h2>内显</h2> -->
        <d-progress percentage='60' strokeWidth='18'/>
        <d-progress percentage='50' strokeWidth='18' />
    </div>
</template>

<script>
import DProgress from './Progress'
export default {
    components:{
      DProgress
    },
    data(){
        return {
            msg:'hello worlds'
        }
    }
}
</script>

<style>
div{
    /* background-color: pink; */
}
</style>
