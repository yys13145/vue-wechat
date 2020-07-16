<template>
  <div id="#app">
    <h1>{{msg}}</h1>
    <div class="content">
      <chat-com :user="data"></chat-com>
      <userlist-com @chooseuser="changeChat" :data="dataList"></userlist-com>
    </div>
  </div>
</template>

<script>
import chatCom from './components/chatcom.vue'
import userlistCom from './components/userlistcom.vue'

export default {
  name: 'App',
  components: {
    chatCom,
    userlistCom
  },
  data(){
    return {
      msg: 'QQ群聊',
      data:{
        name:'张三',
        img: require('./assets/1.jpg'),
        id: 0
      },
      dataList:[
        {
          name:'张三',
          img: require('./assets/1.jpg'),
          id: 0
        },
        {
          name:'李四',
          img: require('./assets/2.jpg'),
          id: 1
        },
         {
          name:'王五',
          img: require('./assets/3.jpg'),
          id: 2
        },
      ]
    }
  },
  methods:{
    changeChat(index){
      this.data = this.dataList[index];
    }
  }
}
</script>
<style scoped>
  .content{
    display:flex;
    width:800px;
    margin: 0 auto;
  }
</style>
<style>
</style>
