<template>

 <router-link :to="path" tag="li" :exact="exact" class="linkDirect">
  <a>
   <i :class="icon"></i> 
   <span>
    <div class="title">{{title}}</div>
   </span>
  </a>
 </router-link>

</template>

<script>
export default {
 name:"LinkDirect",
 props:{
   icon:String,
   path:String,
   title:String,
   badge:Boolean,
   badgeColor:String,
   textBadge:String,
   exact:{type:Boolean,default:false}
 },
}
</script>
<style scoped lang="scss">
 @import '@/global/css/_global-variable.scss';
 $mainColor:#1d2939;
 $mainBackground:#fff;

 .linkDirect{
     margin-bottom: 2px;
     position: relative;
     height: 35px;

  a:hover,a:active{
     background-color: $colorActive;
     color: #fff;
     box-shadow: 0 3px 0 #00000033;
     transition: all .15s ease-in;

  }

  a{
    color: $colorSidebar;
    padding: 7px 10px;
    text-decoration: none;
    display: flex;
    align-items: center;
    position: relative;
    border-radius: 4px;
    font-size: 13px;
    //transition: all .15s ease-in;

  
  >i:first-of-type {
     font-size: 16px;
     vertical-align: middle;
     margin-right: 12px;
     width: 16px;
     display: flex;
     justify-content: center;
     align-items: center;
 }
 }
 }

 //*************LEFT PANEL COLLAPSED *******/

 .leftpanel-collapsed{
  .linkDirect{
   a:hover{
    transition: all .1s .15s ease-in;
   }
   a{
    padding: 10px;
    box-shadow: none;
    justify-content: center;
    transition: all 0s ease-in;

    span{
     overflow: hidden;
     padding: 0;
     max-height: 0;
     max-width: 0;
     //padding-left: 20px;
     //height: 36px;
     position: absolute;
     left: 35px;
     top: 0;
     //min-width: 214px;
     text-align: left;
     z-index: 100;
     color: $colorSidebar;
     //display: none;
     transition: all 0.15s .15s ease-out;
     div.title{
       display: flex;
       align-items: center;
       height: 36px;
       color:transparent;
       //transition: color .15s .15s ease-in;
    }


    /*padding-left: 20px;
    height: 36px;
    position: absolute;
    left: 35px;
    top: 0;
    min-width: 209px;
    text-align: left;
    z-index: 100;
    color: $colorSidebar;
    border-radius:0px 4px 4px 0px;
    align-items: center;
    display: none;*/
    }
    >i:first-of-type { margin-right: 0px; }
   }
  }
  .linkDirect:hover{
   a{
    border-radius: 4px 0 0 4px;
   }
   span{

    background-color: $colorActive;
    border-radius:0px 4px 4px 0px;
    padding-left: 20px;
    min-height: 36px;
    min-width: 214px;
    transition: all 0.15s .15s ease-in;
    div.title{
     color:$colorSidebar;
     transition: color .15s .15s ease-in;
    }

    /*display: flex !important;
    background-color: $colorActive;
    color:$colorSidebar;*/
   }
  }
  .router-link-exact-active.router-link-active:hover{
   a{
    border-radius: 4px 0 0 4px;
   }
   span{

   background-color: $backgroundActive !important;
   padding-left: 20px;
   min-height: 36px;
   min-width: 214px;
   transition: all 0.15s .15s ease-in;
   div.title{color:$colorActive !important;}

   /* display: flex !important;
    background-color: $backgroundActive;
    color: $colorActive;*/
   }
  }
 }
 .badgeRight {
     position: absolute;
     right: 3px;
 }

 .router-link-exact-active.router-link-active{
   background:$backgroundActive;
   border-radius: 4px;
   a,a:hover{
    background: $backgroundActive;
    border-radius: 4px;
   }
  
  
  span,i,.nav-hover{
   color:$colorActive
  }

 }

</style>



