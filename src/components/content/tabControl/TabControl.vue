<template>
  <div class="tab-control">
        <div v-for="(item,index) in titles" 
        class="tab-control-item"
        :class="{active:index === currentIndex}" @click="itemclick(index)"> 
          <span>{{item}}</span>
        </div>
  </div>
</template>

<script>
export default {

props:{
  titles:{
    type:Array,
    default(){
      return []
    }
  }
},
data(){
  return{
    currentIndex: 0,
  }
},
methods:{ 
  itemclick(index){
    this.currentIndex = index
    this.$emit('tabClick',index)
  }
}
}
</script>

<style scoped>
.tab-control{
  display: flex;
  text-align: center;
}
.tab-control-item{
  flex:1;
  height: 40px;
  line-height: 40px;
}

.tab-control-item span{
    padding: 5px
}
.active {
  color: red;
  
}
.active span{
    border-bottom: 3px solid
}
</style>