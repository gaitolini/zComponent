<template>
  <div class="overlay confirm" v-if="isShow">
    <div class="popup">
      <div class="hd">
        <div class="head-icon">
          <!--<img src="../../assets/img/icon-confirm.svg" alt="icon-confirm">-->
        </div>
        <div class="hd-tittle">{{title}}</div>
      </div>
      <div class="bd">{{content}}</div>
      <div class="ft">
        <button v-if="isOKButton" class="btn-x btn-x-default btn-x-type1" @click="okCallback">确定</button>
        <button v-if="isCancelButton" class="btn-x btn-x-default btn-x-type2" @click="cancelCallback">取消</button>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'Confirm',
    data () {
      return {
        isShow: true
      }
    },
    props: {
      isOKButton: {
        type: Boolean,
        default: true
      },
      isCancelButton: {
        type: Boolean,
        default: true
      },
      title: {
        type: String,
        default: ''
      },
      content: {
        type: String,
        default: ''
      },
      okCallback: {
        type: Function,
        default: function () {
          this.isShow = false
        }
      },
      cancelCallback: {
        type: Function,
        default: function () {
          this.isShow = false
        }
      }
    }
  }
</script>
