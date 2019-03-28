<template>

 <ul class="list-group">
       
          <li class="list-group-item">
            <div class="handle">
              <a @click="deleteitem"  href="javascript:;">删除</a>
            </div>
            <p class="user"><span>{{comment.username}}</span><span>说:</span></p>
            <p class="centence">{{comment.content}}</p>
          </li>
        </ul>
</template>

<script>
export default {
 props:['comment','index','delecomment'],
  data(){
   return {

   }
  },
  methods:{

      deleteitem(){
        const {comment,index,delecomment} = this //结构赋值的思想

        if(window.confirm(`确定删除${comment.username}的评论吗`)){
             delecomment(index)
        }
      }
  }
}
</script>

<style scoped>

</style>
