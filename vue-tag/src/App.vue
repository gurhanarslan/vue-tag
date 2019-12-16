<template>
<div>
   <tags v-model="tags" tagColor="primary"  @input="tags.push($event)"></tags>
   <hr>
   <tags v-model="tags" tagColor="danger"  @input="tags.push($event)"></tags>

     <tags v-model="tags" tagColor="success"  @input="tags.push($event)"></tags>
     <tags v-model="tags" tagColor="info"  @input="tags.push($event)"></tags>
     <tags v-model="tags" tagColor="warning"  @input="tags.push($event)"></tags>
     <tags v-model="tags" tagColor="straw"  @input="tags.push($event)"></tags>

     <tags v-model="tags" tagColor="secondary"  @input="tags.push($event)"></tags>
</div>


</template>

<script>
  import tags from './components/tags'
export default {
  components:{
 tags,
  },
 data(){
   return{
     tags:"deneme,text"
   }
 },
  methods:{
  
 
  }
 
}
</script>

<style>
body{
  font-family: sans-serif
}

.tag-box{
  background-color: yellow;
  font-size:14px;
  padding: 10px 0;
  margin-left: 20px;
  border:1px solid #ccc;
  border-radius: 10px
}
.tag{
  margin: 20px;
}
.close{
  color:white;
  background: red;
  border-radius: 10px;
  padding:11px;
  
  cursor: pointer;
  
}
.close:hover{
  background: #ccc;
  color: red;
  transition: all 0.5s linear 
}
</style>
