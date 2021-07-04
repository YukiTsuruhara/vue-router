<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button @click="checkInfo">route 情報</button><br><br>
    <button @click="goHome">Homeに戻る</button>
  </div>
</template>

<script>
export default {
  name:"About",
  methods: {
    checkInfo(){
      console.log(this.$route.path);
      console.log(this.$router);
    },
    goHome(){
      this.$router.push('/')
    }
  },
  beforeRouteLeave (to, from, next) {
    const leave = window.confirm('本当にこのページを離れますか？')
    if(leave) {
      next()
    }else {
      next(false)
    }
    }
}
</script>