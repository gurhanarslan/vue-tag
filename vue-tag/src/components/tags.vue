<template>
   <div class="container-tag">
     <tag :tagColor="tagColor" @closeTagEvent="closeTag($event)" v-for="(tag,index) in tags" :tag="tag" :index="index"></tag>
      <input  type="text" placeholder="Add new Tag!" @keydown.enter="pushtag($event)" @keydown.backspace="removeTag">

  </div>
</template>

<script>
import tag from './tag'
export default {
    components:{
        tag,
    },
    data(){
        return{
            err:"",
            tags:[]
        }
    },
    props:{
        value:{
            required:false
        },
        tagColor:{
            default: 'danger',
            required : false
        }
    },
    methods:{
          pushtag(event){
      let text = event.target;
      this.result=true
      this.tags.forEach(tag=>{
        if(tag.toLowerCase()===text.value.toLowerCase()){
          this.err="Bu Tagı daha önce eklemiştiniz!"
          setTimeout(()=>{
                this.err=""
          },2000)
            this.result=false
    
        }
       
      })
       if(this.result){
         this.tags.push(text.value)
         this.$emit('input', this.tags.join(','))
         text.value=""
       }

      
      
      
      //this.tags.push(event.target.value)
    },
     removeTag(e){
       if(e.target.value.length<=0){
           this.tags.pop();
                this.$emit('input', this.tags.join(','))
       }
  },
     closeTag(index){
    this.tags.splice(index,1)
         this.$emit('input', this.tags.join(','))
  }
    },
    
    created(){
        if(this.value){
            if(this.value.length>0){
               this.tags = this.value.split(',')
            }
        }
    }
    
}
</script>

<style scoped>
.container-tag{
  
  padding: 10px;
}
input{
    border-radius: 5px;
    background-color: rgb(224, 218, 218);
    padding:8px;
    border-style: none;
    
}
</style>