# darkmode
this how to make dark mode 
darkmode.vuejs :
<template>
  <div :class="[dark =='yes'?'dark w-full bg-black p-[50px]':'w-full p-[50px]']">
      <div class="w-[40px] h-[20px] cursor-pointer dark:border-gray-100 rounded-full border-2 border-gray-700 relative" @click="Dark()"><span class="w-[50%] duration-500 rounded-full absolute dark:left-0 top-0 right-0 dark:bg-gray-100 bg-gray-800 h-full"></span></div>
      <div class="dark:text-white">Hussam aldin</div>
      <div class="dark:text-white">Profile of hussam</div>
      <div>
          <input type="text" class="border-2 dark:border-gray-500 border-blue-500 bg-indigo-50">
      </div>
  </div>
</template>

<script>
export default {
data(){
    return{
     dark:this.$store.state.dark,
    }
},
methods:{
    Dark(){
        if(this.dark === 'yes'){
localStorage.setItem('darkmode','no')
this.dark=localStorage.getItem('darkmode')
        }
        else{
localStorage.setItem('darkmode','yes')
this.dark=localStorage.getItem('darkmode')

        }

    }
},
mounted(){
    console.log(this.dark)
}
}
</script>

<style>

</style>


Store.js :
import { createStore } from "vuex";

export default createStore({
  state: {
    dark:localStorage.getItem('darkmode')|| 'no'
  },
  getters: {},
  mutations: {
  },
  actions: {},
  modules: {},
});
