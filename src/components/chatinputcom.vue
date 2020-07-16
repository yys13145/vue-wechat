<template>
  <div>
    <input   @keydown.enter="add" v-model="message" type="text" />
    <button @click="add">发送</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: '',
    };
  },
  methods: {
    add(){
      this.send(this.message);
      this.message = '';
    }
  },
  props:[
    'send'
  ]
};
</script>

<style scoped>
</style>