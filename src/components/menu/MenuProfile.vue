<template>
  <ul>
   <router-link @click.native="Current" :to="li.to" tag="li" v-for="li in Links" :key="li.key">
    <a><i :class="li.icon"></i><span v-text="li.textLink"></span></a>
   </router-link>
   </ul>
</template>

<script>
export default {
 name:"MenuProfil",
 data() {
  return {
   Links:[
    {
      key:1,
      icon:"fa fa-user",
      textLink:"Profile",
      to:"/profile"
    },
    {
      key:2,
      icon:"fa fa-cog",
      textLink:"Account Settings",
      to:"/Settings"
    },
    {
      key:3,
      icon:"fa fa-question-circle",
      textLink:"Help",
      to:"/Help"
    },
    {
      key:4,
      icon:"fas fa-sign-out-alt",
      textLink:"Sign Out",
      to:"/Sign"
    },
   ],
  };
 },
 methods: {
  Current(){
   let el = document.querySelector(".nav-parent.active");
   if(el != null) el.classList.remove("active");}
 },
}
</script>
