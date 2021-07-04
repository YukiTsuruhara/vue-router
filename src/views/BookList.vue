<template>
  <div>
      <h2>本の紹介</h2>
      <ul>
        <li
         @click="showBookDetail(book.id)"
         v-for="book in books"
         :key="book.id"
         ><span>{{ book.title }}</span>
         </li>        
      </ul>
  </div>
</template>

<script>
export default {
    name:"BookList",
    data(){
      return{
        bookIndex:-1,
        books:[
          {id:1, title:"ヴェノム", content:"マーベルシリーズ"},
          {id:2, title:"ピーターパン", content:"ファンタジー"},
          {id:3, title:"ライジン24", content:"堀口恭二"}
        ]
      }
    },
    methods:{
      showBookDetail(id){
        this.bookIndex = id -1
        this.$router.push({
          name:"Book",
          params:{
            id: this.books[this.bookIndex].id,
            title: this.books[this.bookIndex].title,
            content: this.books[this.bookIndex].content
          }
        })
      }
    }
}
</script>

<style scoped>
  ul {
    width: 50%;
    margin: 0 auto;
    text-align: left;
    list-style: none;
  }
  span {
    position: relative;
    font-weight: bold;
    cursor: pointer;
  }
  span:after {
    content: '';
    position: absolute;
    left: 0;
    bottom: -10px;
    width: 0%;
    height: 2px;
    background-color: red;
    transition: all 0.3s ease;
  }
  li:hover span:after {
    width: 100%;
  }
  li:not(:first-child) {
    margin-top: 30px;
  }
</style>