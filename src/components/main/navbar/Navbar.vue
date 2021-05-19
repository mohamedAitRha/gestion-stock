<template>
 <div class="navbar">
  <div class="navbarContent">
   <div class="create">

    <menu-toggle />

    <i class="fas fa-plus-circle"></i>
    <i class="fas fa-history"></i>
   </div>
   <search-dropdown/>
   <div class="header-right">
    <div class="menu-content">
     <div class="btnNav">
      <i class="fas fa-bell"></i>
     </div>
     <div class="btnNav">
      <i class="fas fa-cog"></i>
     </div>
     <div class="btnNav">
      <i class="far fa-question-circle"></i>
     </div>
     <div class="btnNav">
      <img class="imgUser" src="@/images/loggeduser.png"/>
     </div>
    </div>
   </div>
  </div>
 </div>
</template>
<script>
import searchDropdown from './input/searchDropdown';
import MenuToggle from './menu/MenuToggle.vue';
export default {
 components: { 
  searchDropdown,
  MenuToggle 
  },

}
</script>

<style lang="scss" scoped>

@import '@/global/css/_global-variable.scss';

 .desplayBetween{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.leftpanel-collapsed{
 .navbar{
  margin-left: -50px;
 }
}
 .navbar{
  text-transform: capitalize;
  @extend .desplayBetween;
  justify-content: flex-start;
  background-color:$mainBackgroud;
  padding:0;
  border:0px solid $backgroudLogo;
  border-width: 0px 0px 1px 0px;
  
  .navbarContent{
   display: flex;
   align-items: center;
   padding: 0 8px;
   flex-grow: 4;
   i,a{
       font-size: $font-size-icon;
       color: $color-navbar-icon;
       cursor: pointer;
      }
   i:active,a:active,img.imgUser:active{
       transform: scale(.95);
      }
     .create{
      width: 122px;
      @extend.desplayBetween;
      justify-content: space-around;
      margin-right: 20px;
      
     }
     .header-right{
      flex-grow: 3;
      .menu-content{
       @extend .desplayBetween;
       justify-content: flex-end;
       div{
        padding: 5px 20px;
       
        img{
         width: 35px;
         height: 35px;
         border-radius: 50%;
         border:1px solid $color-navbar-icon;
         cursor:pointer;
        }
        i{ 
         cursor: pointer;
         font-size: 1.2rem;
        }
       }
      }
     }
  }

}
</style>