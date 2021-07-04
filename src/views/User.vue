<template>
  <div>
      <h2>ユーザー情報</h2>
      <router-link to="profile">ユーザープロフィール</router-link>  |
      <router-link to="post">ユーザ記事</router-link>
      <div class="green">
        <router-view/>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.green {
    border: 2px solid green;
}

</style>