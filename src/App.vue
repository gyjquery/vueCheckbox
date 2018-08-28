<template>
  <div id="app">
     <ul v-for="(item,index) in arr" :key="index">
       <li>
         <label :for="index" class="iconfont icon-duihao1" :class="{activeIcon:item.isChecked}"><input type="checkbox" :id="index" v-model="item.isChecked"></label><div>{{item.userName}}</div>
       </li>
     </ul>
    <input type="text" placeholder="这是选择的数据" v-model="acc"/><span @click="addContent">确定</span>
  </div>
</template>

<script>
  const arr =[
    {
      userName:"张三",
      userId:1,
      age:19
    },
    {
      userName:"李四",
      userId:2,
      age:18
    },
    {
      userName:"赵五",
      userId:3,
      age:17
    }

  ]
export default {
  name: 'App',
  data(){
    return{
       arr:[],
       acc:""
    }
  },
  mounted(){
    arr.forEach((item,index)=>(
       item.isChecked=false
    ))
    this.arr=arr

  },
  methods:{
    addContent(){
      let str=""
       this.arr.forEach((item,index)=>{
         if(item.isChecked){
           str+=item.userName+" "
         }
       })
    this.acc=str
    }
  }
}
</script>

<style scoped>
    ul{
       list-style: none;
    }
  ul li{
    margin: 0;
    madding:0;
    height:50px;
    display: flex;
    align-items: center;
    margin-bottom: 4px;
  }
  ul li div{
    width:200px;
    height:50px;
    background: deepskyblue;
    text-align: center;
    line-height: 50px;
    margin-left: 10px;
    border-radius: 5px;
  }
  label{
    display: inline-block;
    border-radius: 50%;
    border:1px solid #ccc;
    font-size: 30px;
    width:30px;
    height:30px;
    text-align: center;
    line-height: 30px;
    overflow: hidden;
  }
    label input{
       display: none;
    }
    .icon-duihao1{
      color: #fff;
    }
  .activeIcon{
    color: deepskyblue;
  }
  span{

  }

</style>
