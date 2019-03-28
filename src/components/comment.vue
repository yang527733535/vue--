<template>
 <div class="col-md-4">
        <form class="form-horizontal">
          <div class="form-group">
            <label>👁用户名</label>
            <input  v-model="username" type="text" class="form-control" placeholder="用户名">
          </div>
          <div class="form-group">
            <label>👁评论内容</label>
            <textarea  v-model='comment' class="form-control" rows="6" placeholder="评论内容"></textarea>
          </div>
          <div class="form-group">
            <div class="col-sm-offset-2 col-sm-10">
              <button @click='add' type="button" class="btn btn-default pull-right">提交</button>
            </div>
          </div>
        </form>
      </div>
</template>

<script>
export default {
  props:['addcomment'],
  data(){
   return {
       username:"",
       comment:""
   }
  },
  methods:{
      add(){
          //1检查输入的合法性，
        const username = this.username
        const content = this.comment
        if(!username||!content){
            alert('用户名和评论不能为空👀')
            return
        }
          //2根据输入的数据，封装成一个comment对象
        const comment ={
            username,
            content
        }

          //3添加到app.vue中的comments中去
            this.addcomment(comment)

          //4清空this.username和this.content
          this.username=this.comment = ''
      }
  }
}
</script>

<style scoped>

</style>
