<template>
    <div class="userlist">
        <h1>用户列表</h1>
        <ul>
            <li v-for="(item,index) in data" :key="item.id" @click="choose(index)">
                <p>{{item.name}}</p>
                <img :src="item.img">
            </li>
        </ul>
    </div> 
</template>
<script>
export default {
    data(){
        return{

        }
    },
    methods:{
        choose(index){
            this.$emit('chooseuser',index);
        }
    },
    props:['data']
}
</script>
<style scoped>
    .userlist{
        width: 300px;
        background: #ccc;
        text-align: center;
    }
    .userlist ul li{
        display: flex;
    }
    .userlist ul li img{
        width: 80px;
        height: 80px;
    }
</style>