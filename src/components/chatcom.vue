<template>
    <div class="chat">
        <h1>{{user.name}}加入了聊天</h1>
        <div class="chatlist">
           <chat-item v-for="(item,index) in chatList" :chat="item" :key="'chat'+index">
               {{item.chatcontent}}
           </chat-item>
        </div>
        <chat-input :send="add"></chat-input>
    </div> 
</template>
<script>
import chatInput from './chatinputcom.vue'
import chatItem from './chatitem.vue'
export default {
    data(){
        return{
            chatList: [
                {
                    chatcontent: "几点回来？",
                    user:{
                        name: '赵柳',
                        img: require('../assets/1.jpg')
                    }
                }
            ]
        }
    },
    methods:{
        add(value){
            this.chatList.push({
                chatcontent:  value,
                    user:{
                        name:this.user.name,
                        img:this.user.img
                    }
            })
        }
    },
    props:['user'],
    components:{
        chatInput,
        chatItem
    }
}
</script>
<style scoped>
    .chat{
        width: 500px;
        height: 700px;
        border: solid 1px #eee;
        margin-right: 2px;
    }
</style>