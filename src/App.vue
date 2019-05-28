<template>
   <div class="abc">
     <h3>留言卡</h3>
     <input type="text" v-model="text" placeholder="请输入信息.....">
     <button @click="handleClick">提交</button>
     <ul class="">
       <li v-for="(item,index) in list" :key="index" @click="removeItem(index)">
           {{item}}
         </li>
     </ul>
   </div>
</template>

<script>
export default {
  data(){
    return({
      list:[
        '第一条数据',
        '第二条数据',
        '第三条数据'
      ],
      text:''
    })
  },
  methods:{
    handleClick(){
      // console.log(this.text)
      this.list.push(this.text)
      this.text=''
      // console.log(this.list)
    },
    removeItem(index){
      this.list.splice(index,1)
    }
  }
}

</script>

<style>

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #203f5e;
  margin-top: 60px;
}

.abc{
  margin: 0 auto;
  margin-top:5%;
  width: 280px;
  height: 430px;
  border-radius: 20px;
  background:url(../src/assets/1.png);
}
.abc h3{
  margin:  0 auto;
  margin-top: 1%;
  font-size: 30px;
  color:#1e1e1e;
  width: 100px;

}
.abc input{
  margin: 0 auto;
  margin-left: 8px;
  margin-top: 30%;
  border-radius: 5px;
  border:1px solid #dadd0e;
  width: 200px;
  height: 20px;;

}
.abc button{
   margin: 0 auto;
   margin-top: 20px;
   margin-left: 8px;
   background: #dadd0e;
}
.abc ul {
   margin: 0 auto;
   margin-top: 23%;
   width: 50%;
   color:blueviolet;
}
</style>
