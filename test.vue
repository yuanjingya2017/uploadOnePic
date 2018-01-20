<template>
  <uploadPic @getSonData="getSData"></uploadPic>
</template>

<script>
  import uploadPic from './uploadPic'
  export default {
  data(){
    return {
      //保存图片base64的数组
      pics:[]
    }
  },
  mounted(){

  },
  components:{
    uploadPic
  },
  computed:{

  },
  methods:{
    getSData:function (value) {
      var _this = this;
      _this.pics = value;
      console.log(value)
    }
  }
};
</script>
<style scoped>

</style>
