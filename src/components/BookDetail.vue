<template>
  <div>
      <h2>本の詳細</h2>
      <table>
          <tr>
              <td>本のタイトル</td>
              <td>{{ this.books[this.bookIndex].title }}</td>
          </tr>
          <tr>
              <td>本の内容</td>
              <td>{{ this.books[this.bookIndex].content }}</td>
          </tr>
      </table>
  </div>
</template>
<script>
export default {
    props: {
        id: Number,
        title: String,
        content: String
    },
    data(){
      return{
        bookIndex:this.$route.params.id -1,
        books:[
          {id:1, title:"ヴェノム", content:"マーベルシリーズ"},
          {id:2, title:"ピーターパン", content:"ファンタジー"},
          {id:3, title:"ライジン24", content:"堀口恭二"}
        ]
      }
    },
    created(){
      if(this.$route.params.id > this.books.length) {
        this.$router.push('/book')
      }
    }
}
</script>

<style>
    table {
        width: 50%;
        margin: 0 auto;
        text-align: left;
        font-weight: bold;
    }

    tr:nth-child(2n) {
        background-color: rgb(224, 221, 221);
    }

    td:first-child {
        margin-right: 20px;
    }
</style>