<script setup>
import BaseListRepo from "./components/BaseListRepo.vue";
import { ref, reactive } from "vue";
 let  submitRepos = reactive([]);
let gitrepoInput = ref("");
let projectTInput = ref("");
 let clickConfrim = () => {
  submitRepos.push({
    gitRepo: gitrepoInput.value,
    projectTitle: projectTInput.value,
  });

};
const  currentStatus = 'USER_CONFIRM'
</script>

<template>
  <div class="container">
    <div class="content">
      <div>
        <h1>INT204 Student Project</h1>
      </div>
      <div class="inputGit">
        <input
          type="text"
          v-model="gitrepoInput"
          placeholder="Input git repo"
        />
      </div>
      <div class="inputProject">
        <input
          type="text"
          v-model="projectTInput"
          placeholder="Input project input"
        />
      </div>
      <div class="add-content">
        <button class="add" @click="clickConfrim">Add</button>
      </div>
      <div class="status">
        <p v-show="true" >Current Status : {{currentStatus}} </p>
      </div>
    </div>
    <BaseListRepo :items = submitRepos  />
  </div>
</template>

<style >
.status{
  padding-top: 40px;
}
.add-content {
  padding-top: 20px;
  text-align: center;
}
.add {
  cursor: pointer;
  background-color: rgb(212, 186, 71);
  font-size: 16px;
  width: 200px;
}
.add:hover {
  background-color: rgb(228, 228, 181);
}
input {
  width: 400px;
  height: 30px;
}
.inputGit {
    padding-top: 20px;
  padding-bottom: 40px;
}

h1,
.inputGit,
.inputProject {
  text-align: center;
}
*{
  padding: 0;
  margin: 0;
}
.container {
  display: grid;
  grid-template-columns: auto auto;
  background-size: cover;
  height: 100vh;
  width: 100vw;
  background-color: rgb(63, 63, 155);
}
.content {
  padding-top: 20px;
  justify-self: self-start;
  align-self: center;
  background-repeat: no-repeat;
  width: 500px;
  height: 500px;
  background-color: white;
  border: 4px solid black;
}
</style>
