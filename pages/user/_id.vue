<template>
  <div>
    修改用户信息{{id}},名称：{{name}}
  </div>
</template>
<script> 
  export default {
    layout:'test',
    async asyncData(){
      //alert(0)无法在服务端运行
      //请求服务端接口

      //先调用a方法
      var a = await new Promise(function(resolve,reject){
        setTimeout(function () {
          console.log(1)
          resolve(1)
        },2000)
      });

      //在调用b
      var b = await new Promise(function(resolve,reject){
        setTimeout(function () {
          console.log(2)
          resolve(2)
        },2000)
      });

      return{
        name:"请求服务端接口返回了！"
      }
    },
    data(){
      return{
        id:'',
        name:''
      }
    },
    methods:{
      getUser:function () {

        //ajax请求服务接口
        this.name = "君若"
      },
      a(){
        return new Promise(function(resolve,reject){
          setTimeout(function () {
            resolve(1)
          },2000)
        })
      },
      b(){
        return new Promise(function(resolve,reject){
          setTimeout(function () {
            resolve(2)
          },1000)
        })
      }
    },
    mounted(){
      this.id = this.$route.params.id;
      //this.getUser();
      /*this.a().then(res=>{
        alert(res)
        console.log(res)
      })
      this.b().then(res=>{
        alert(res)
        console.log(res)
      })*/

    }
  }
</script>
<style>


</style>
