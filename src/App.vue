<template>
    <div>

    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>🏠请发表对mrhh的评论</h1>
          </div>
        </div>
      </div>
    </header>
   <comment :addcomment='addcomment' ></comment>
   <commentlist :delecomment='delecomment' :comments='comments' ></commentlist>
</div>
</template>

<script>
import comment from './components/comment.vue'
import commentlist from './components/commentlist.vue'
export default {
  data(){
    return {
      comments:[
        {
          username:"🏠bob",
          content:"vue真好呀"
        },
         {
          username:"jack",
          content:"📚我该说些什么呢"
        },
         {
          username:"tom",
          content:"wuwuwu"
        }
      ]
    }
  },
  components:{
    comment,
    commentlist
  },
  created(){
 this.delecomment(2)
  },
  methods:{
    addcomment(comment){
      this.comments.unshift(comment)
    },
    delecomment(index){
    this.comments.splice(index,1)
    console.log(index);
  }
  }
    
  
}
</script>

<style>

</style>
