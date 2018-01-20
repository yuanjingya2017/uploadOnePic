<template>
  <div>
    <li v-for="pic in pics">
      <a href="javascript:;" class="comments_ordershare_con_b_a">
        <img :src="pic" alt="">
      </a>
      <a href="javascript:;" class="comments_ordershare_con_b_c" @click="delPics(pic)"></a>
    </li>
    <li>
      <a href="javascript:;" class="comments_ordershare_con_b_a">
        <img src="../assets/images/busin/comments_orders_btn.png" alt="">
        <input type="file" @change="onFileChange">
      </a>
    </li>
  </div>
</template>

<script>
    export default {
      data(){
        return {
          pics:[]
        }
      },
      mounted(){

      },
      methods:{
        //上传图片 监听是否文件有改变
        onFileChange(e) {
          this.click = true;
          var files = e.target.files || e.dataTransfer.files;
          if (!files.length)
            return;
          this.createImage(files[0]);
        },
        //将图片保存到数组 并且显示在页面上
        createImage(file) {
          var _this = this;
          var reader  = new FileReader();
          reader.addEventListener("load", function () {
            _this.pics.push(reader.result);
          }, false);
          if (file) {
            reader.readAsDataURL(file);
          }
          this.$emit('getSonData',_this.pics);
        },
        //删除图片
        delPics:function (item) {
          var _this = this;
          for(var i=0;i<_this.pics.length;i++){
            if(_this.pics[i]==item){
              _this.pics.splice(i,1);
              break;
            }
          }
        }
      }
    };
</script>

<style scoped>

</style>
