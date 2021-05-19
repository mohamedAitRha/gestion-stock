<template>
   <a @click="SidebarShowToggle" class="menutoggle">
    <i class="fa fa-bars"></i>
   </a>
</template>

<script>
export default {
 
 methods:{
  SidebarShowToggle(){
   if(window.innerWidth > 1024){ 
    document.body.classList.toggle("leftpanel-collapsed");
    document.body.classList.remove("chat-view");
   } 
   else{ 
    document.body.classList.toggle("leftpanel-show");
    document.body.classList.remove("chat-view-small");
    }

   (window.innerWidth < 1024) ?
   (document.body.classList.contains("leftpanel-show")) ? document.querySelector(".header-right").classList.add("d-none") : document.querySelector(".header-right").classList.remove("d-none") : document.querySelector(".header-right").classList.replace("d-none" , "d-block") 
  },
 },
 
}
</script>

<style lang="scss" scoped>
 @import '@/global/css/_global-variable.scss';
 a{
  cursor: pointer;
 }
 a:active{
  transform: scale(.98);
 }
</style>