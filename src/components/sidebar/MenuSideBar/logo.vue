<template>
  <div class="logo">
      <a>
        <span class="badge bg-danger">G</span>
        <span class="badge bg-success">e</span>
        <span class="badge bg-primary">s</span>
        <span class="badge bg-warning">t</span>
        <span class="badge bg-danger">i</span>
        <span class="badge bg-primary">o</span>
        <span class="badge bg-success">n</span>
      </a>
  </div>
</template>

<style lang="scss" scoped>
@import "../../..//global/css/global-variable.scss";

 .leftpanel-collapsed{
  .logo{
   display: none;
  }
 }

  .logo{
  background-color: $backgroudLogo;
  padding: 0 20px;
  border-right: 1px solid #e4e4e4;
  a{
   display: flex;
   height: 45px;
   align-items: center;
   justify-content: center; 
   padding:10px 15px;
   width: 100%;
   >.bg-danger:first-child{
    text-transform: uppercase;
   }
   
   .bg-danger{
   transform:skew(-14deg, 17deg);
  }
 
  .bg-success{
   transform: rotateZ(-25deg);
  }
 
  .bg-primary{
   transform: rotate3d(1,1,1,9deg);
  }


 .badge:hover{
  transform: scale(1.5);
  z-index: 999;
  box-shadow:2px 2px 5px 1px #5c5b5b;
  font-weight: bold;
 }

  .badge{
   font-weight: 600;
   font-size: 70%;
   margin: 0 1px;
   display: flex;
   align-items: center;
   justify-content: center;
   flex-grow: 1;
   padding: 4px;
   text-transform: uppercase;
   min-width: 22px;
   transition: transform .15s,font-weight .15s .15s linear;
   box-shadow: 2px 2px 6px 0px #6b6969;
  }


  }
 
 }
</style>