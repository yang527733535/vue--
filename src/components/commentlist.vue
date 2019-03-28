<template>
 <div class="col-md-8">
     <h3 class="reply">❤️评论回复👌</h3>
     <h2 v-show="comments.length==0">❤️暂无评论,点击左侧添加评论</h2>
    <listitem  :delecomment='delecomment' :index='index' :comment='comment' :key="index" v-for="(comment,index) in comments"></listitem>

    </div>
</template>

<script>
import listitem from './listitem.vue'
export default {
  props:['comments','delecomment'],
  components:{
      listitem
  },
  data(){
   return {

   }
  }
}
</script>

<style scoped>

</style>
