<template>
  <div>
      <h1>NotFound</h1><br><br>
      <button @click="goHome">Home</button>
  </div>
</template>

<script>
export default {
    methods:{
        goHome(){
            this.$router.push('/')
        }
    }
}
</script>

<style scoped>
    div {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
    }
    button {
        width: 200px;
        height: 50px;
        font-size: 20px;
        border: none;
        border-radius: 10px;
        transition: all .5s ease;
    }
    button:hover {
        background-color: greenyellow;
    }
</style>