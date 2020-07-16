<template>
  <div class="chat-item">
     <img :style="imgstyle" :src="chat.user.img" alt="">
     <div>
        <slot></slot>
     </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            imgstyle: {
               width: "60px",
               height: "60px"
            }
        }
    },
    methods:{
    },
    props:['chat']
}
</script>

<style scoped>
.chat-item{
   display: flex;
}
</style>