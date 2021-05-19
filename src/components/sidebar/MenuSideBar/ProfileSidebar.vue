<template>
 <div>
   <form class="searchform input-group side" action="index.html" method="post">
     <input type="text" class="form-control" name="keyword" placeholder="Search here...">
   </form>

   <div class="media userlogged">
     <img
       alt=""
       :src="user.userImage"
       class="media-object"
     />
     <div class="media-body">
       <h4>{{user.name}}</h4>
       <span>{{user.userText}}</span>
     </div>
   </div>

    <h5 class="sidebartitle">Account</h5>
    <Menu-profile class="nav nav-pills nav-stacked nav-bracket mb30 display"/>
 </div>
</template>

<script>
import img from "@/images/loggeduser.png";
import MenuProfile from '../../menu/MenuProfile.vue';
export default {
 components:{
  MenuProfile,
 },
 data() {
  return {
   user:{
    name:"Ait rha med",
    userImage:img,
    userText:"Life is so..."
   },
  }
 },
 name:"ProfileSidebar",
}
</script>