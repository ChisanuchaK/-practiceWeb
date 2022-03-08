<script setup>
import {ref} from 'vue'
   let props = defineProps({
     items: {
       type:[Array] ,
       require: true 
     }
   })
let showStatus = ref(false)
    let clickConfirm = ()=>{
     showStatus.value = true
         
    }

</script>

<template>
  <div class="content-list">
    <div>
      <h1>INT204 Student Project List</h1>
    </div>
      <div class="scroll">
          <div class="object" v-for="(item , index) in items" :key="index">
            <p>{{item}}</p>
        </div>
      </div>
        <div class="button-confirm">
          <button @click="clickConfirm" class="confirm">
            confirm
          </button>
        </div>
  </div>

  
</template>

<style scoped>
.scroll{
    overflow: auto;
}
  .object{

    text-align: center;
    padding: 20px 0  20px 0;
  }
  .button-confirm{
    text-align: center;  }
.confirm{
  cursor: pointer;
  background-color: rgb(212, 186, 71);
  font-size: 16px;
  width: 200px;
}
.content-list {
    padding-top: 20px;
  justify-self: self-end;
  align-self: center;
  padding-left: 10px;
  background-repeat: no-repeat;
  width: 500px;
  height: 500px;
  background-color: white;
  border: 4px solid black;
}
</style>
