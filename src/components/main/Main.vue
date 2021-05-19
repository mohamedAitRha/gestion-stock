<template>
 <div class="main">
  <navbar />
  <router-view />
 </div>
</template>
<script>
import Navbar from './navbar/Navbar';
export default {
 components:{
  Navbar
 }
}
</script>

<style lang="scss" scoped>

 @import "../../global/css/_global-variable.scss";
.leftpanel-collapsed{
 .main{
 margin-left: 50px;
 }
}

.main{
 margin-left: 240px;
 height: 1000px;
 background-color: $mainBackgroud;
}

</style>