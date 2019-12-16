<template>
<span>
      <span class="tag-box" :class="tagColor" >
    <span class="tag">{{tag}}</span>
    <span @click="$emit('closeTagEvent',index)" class="close"  :class="tagColor">X</span>
   
  </span>
</span>
</template>

<script>
export default {
   data(){
       return{
          
       }
   },
   props:["tag","index","tagColor"],
    methods:{
        ColorTag(){
            return this.tagColor
        }
    }
};
</script>

<style scoped>



.primary{
    background-color: rgb(111, 111, 221) !important;
    color: rgb(12, 12, 216) !important;
}
.primary .close{
    background-color: rgb(68, 68, 145) !important;
    color: white !important;
}
.danger{
    background-color: rgb(231, 117, 117) !important;
    color: rgb(223, 21, 21)!important;
}
.danger .close{
    background-color: rgb(219, 66, 66) !important;
    color: rgb(247, 220, 220)!important;
}
.success{
    background-color: rgb(150, 250, 183) !important;
    color: rgb(18, 104, 7)!important;
}

.success .close{
    background-color: rgb(85, 160, 110) !important;
    color: white!important;
}

.straw{
    background-color: #E4D96F !important;
    color: rgb(97, 92, 47)!important;
}

.straw .close{
    background-color: rgb(170, 161, 79) !important;
    color: white !important;
}
.info{
    background-color: #17a2b8 !important;
    color: #0b3f47!important;
}

.info .close{
    background-color: #0c5763 !important;
    color: white !important;
}
.warning{
    background-color:#ffc107 !important;
    color: #755903!important;
}

.warning .close{
    background-color: #c59607 !important;
    color: white !important;
}
.secondary{
    background-color:#6c757d !important;
    color: #3c4044!important;
}

.secondary .close{
    background-color: #4c5257 !important;
    color: white !important;
}

.tag-box{
  background-color: yellow;
  font-size:14px;
  padding: 5px 0;
  margin-left: 20px;
  border:1px solid #ccc;
  border-radius: 8px
}
.tag{
  margin: 20px;
}
.close{
  color:white;
  border-radius: 10px;
  padding:8px;
  
  cursor: pointer;
  
}
.info .close:hover{
  background: #ccc;
  color: red;
  transition: all 0.5s linear 
}
</style>