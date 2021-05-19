<template>
  <div class="home">
   <div class="header">
    <div class="dashboard-tabs">
     <ul class="nav-tabs">
      <li class="nav-item" @click="active = 1">
       <a class="nav-link" @click="active = 1" :class="{'active':active===1}">
        <div class="tour-step">Dasboard</div>
       </a>
      </li>
      <li class="nav-item"  @click="active = 2">
       <a class="nav-link"  @click="active = 2" :class="{'active':active===2}">
        <div class="tour-step">recent update</div>
       </a>
      </li>
     </ul>
    </div>
   </div>
   <div class="body">
    <div class="content-body">
     <div class=" row dashboard-section">
      <div class="col-lg-8 col-md-8 col-sm-8 col-8 sales-activity">
       <label class="pb-3 font-weight-light font-xlarge">Sales Activity</label>
       <div></div>
       <SalesActivity />
      </div>
      <div class="col-lg-4 col-md-4 col-sm-4 col-8 inventory-summary"></div>
     </div>
    </div>
   </div>
  </div>
</template>

<script>
import SalesActivity from "@/components/homeComponents/SalesActivity";
export default {
 data() {
  return {
   active:1,
  }
 },
 components:{
  SalesActivity,
 }
}
</script>

<style lang="scss" scoped>
 @import '@/global/css/_global-variable.scss';

 .home{
  height: 100%;
  background-color: #fff;
  position: relative;
  .fill{
    left: 0;
    right: 0;
    position: absolute;
  }
  /********* START HEADER HOME PAGE ************/
  .header{
    padding: 0 20px;
    border-bottom: 1px solid #eee;
    overflow: visible;
   /* position: fixed;
    right: 0;
    left: 240px;*/

    .nav-tabs{
     display: flex;
     align-items: center;

      li.nav-item{
       a.nav-link{
        font-size: 18px;
        padding: 20px 0 14px;
        margin: 0 13px;
        height: 64px;
        cursor: pointer;
        color: $backgroudBlue;
        transition: color .15s ease-in-out,background-color .15s ease-in-out;
       }
       a.nav-link:hover,a.nav-link:focus,a.nav-link:active{
        font-weight: 500;
        border-color: transparent;
        outline: none !important;
        box-shadow: none !important;
       }
       a.nav-link.active,a.nav-link.active:hover,a.nav-link.active:focus{
        border: none;
        border-bottom: 2px solid $BordercolorBlue;
        color:#495057;
       }
      }
    }
  }
  /********* START BODY HOME PAGE *************/
 .body{
  padding:0;
  overflow: auto;
  height:100%;
  .content-body{
   margin-bottom: 50px;
   .dashboard-section:first-child{
     border-bottom: 1px solid #dde5e8;
     margin-top: 0;
     padding: 0;
     background-color: #f5faff;
   }
   .dashboard-section{
    margin: 40px 0 0;
    padding: 0 20px;
    .sales-activity{
     padding: 30px 0 24px 35px;
     width: 68%;
    }
   }
  }
 }
 }
/********* LEFT PANEL COLLAPSE ********/
.leftpanel-collapsed{
 /*.header{
  left: 50px;
 }*/
}
</style>


