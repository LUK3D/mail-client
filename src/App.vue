<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import SideMenu from './components/SideMenu.vue'
import MailList from './components/MailList.vue'
import MailDetail from './components/MailDetail.vue'
</script>

<template>
<div class="dark w-screen h-screen relative dark:bg-gray-700 bg-gray-100 grid grid-cols-10 overflow-hidden">
  <div class=" col-span-2 sm:col-span-4 lg:col-span-2 dark:bg-gray-700 bg-white h-full">
    <SideMenu></SideMenu>
  </div>
  <div class="col-span-8 sm:col-span-6  lg:col-span-4 h-full flex flex-col">
    <MailList></MailList>
  </div>
  <div :class="`${showDetails?'flex' :'hidden'} z-20  md:flex absolute sm:top-0 lg:relative sm:right-0 sm:col-span-12  lg:col-span-4 h-full bg-white`">
    <MailDetail></MailDetail>
  </div>

</div>
</template>
<script lang="ts">
export default{
  data(){
    return {
      showDetails:false
    }
  }
}

</script>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  padding:0;
  margin:0;
}
</style>
