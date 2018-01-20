# uploadOnePic
//html代码里面添加                  
<uploadPic @getSonData="getSData"></uploadPic>
//script标签里面添加
<script>
import uploadPic from './uploadPic'
data(){
return {
  uploadPic:[]
    }
},
components:{
    uploadPic
},
//methods里面添加方法
methods:{
    getSData:function (value) {
            var _this = this;
            _this.uploadPic = value;
            console.log(value)
    }
}
</script>
