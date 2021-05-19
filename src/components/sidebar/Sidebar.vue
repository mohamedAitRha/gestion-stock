<template>
 <div class="leftpanel">

 <Logo/>

  <div class="leftpanelinner">      
    <h5 class="sidebartitle">Navigation</h5>
    <Menu-Sidebar :Links="MenuJson"/> 
  </div>
</div>
</template>

<script>
import MenuSidebar from './MenuSideBar/MenuSidebar';
import MenuJson from '../../json/Menu.json';
import Logo from './MenuSideBar/logo';
export default {
 data() {
  return {
   MenuJson,
  }
 },
 
 components:{
  MenuSidebar,
  Logo,
 }
}
</script>
<style lang="scss" scoped>

/******* LEFT PANEL COLLAPSE ********/
 .leftpanel-collapsed{
  .leftpanel{
   top:45px;
   width: 50px;

   .leftpanelinner{
    h5{
     display: none;
    }
   }
  }
 }
 .leftpanel{
  transition: width .1s ease-in;
  position: absolute;
  left:0;
  top:0;
  z-index: 100;
  width:240px;
  .sidebartitle {
 font-size: 11px;
 text-transform: uppercase;
 color: #999;
 margin: 10px 0;
 }
.leftpanelinner {
 padding: 5px 15px;
 }
}
.leftpanel-collapsed{
 .leftpanelinner {padding:0px;}
}

</style>