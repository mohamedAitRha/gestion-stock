

<template>
 <ul class="nav nav-pills nav-stacked nav-bracket">

   <Link-direct :class="{'nav-hover':hover}" @click.native="Current" path="/" icon="fa fa-home" title="Dasboard" exact />
   <Dropdowns  :class="{'nav-hover':hover}" v-for="li,index in Links" :key="index" :icon="li.icon" :title="li.title" :children="li.children"/>
   <div class="margin-top"></div>
   <Link-direct v-for="item in group1" :key="item.title" :class="{'nav-hover':hover}" @click.native="Current" :path="item.path" :icon="item.icon" :title="item.title"/>
 
   <Dropdowns  :class="{'nav-hover':hover}" v-for="li in navParent1" :key="li.title" :icon="li.icon" :title="li.title" :children="li.children"/>   
   
   <div class="margin-top"></div>
   <div class="margin-top"></div>

   <Link-direct v-for="item in group2" :key="item.title" :class="{'nav-hover':hover}" @click.native="Current" :path="item.path" :icon="item.icon" :title="item.title"/>

 </ul>
</template>

<script>
import Dropdowns from './DropDownSideBar';
import LinkDirect from '../../menu/LinkDirect';
export default {

 name:"MenuSidbar",
 props:['Links'],
 data(){
  return{
   hover:false,
   active:false,
   group1:[
    {
     title:"customers",
     icon:"far fa-user",
     path:"/customers"
    },
    {
     title:"sales orders",
     icon:"fas fa-shopping-cart",
     path:"/sales orders"
    },
    {
     title:"packages",
     icon:"fas fa-cube",
     path:"/packages"
    },
    {
     title:"invoices",
     icon:"fas fa-file-invoice",
     path:"/invoices"
    },
    {
     title:"payements received",
     icon:"fab fa-stripe-s",
     path:"/payements received"
    },
   ],
   navParent1:[
    {
     title:'return',
     icon:'fas fa-undo',
     children:[
     {
      childText:"sales returns",
      to:"/sales returns"
     },
     {
      childText:"credit notes",
      to:"/credit notes"
     }]
    }
   ],
   group2:[
    {
     title:"vendors",
     icon:"fas fa-box-open",
     path:"/vendors"
    },
    {
     title:"purchase orders",
     icon:"fa fa-shopping-bag",
     path:"/purchase orders"
    },
    {
     title:"bills",
     icon:"fas fa-receipt",
     path:"/bills"
    },
     {
     title:"payements made",
     icon:"fas fa-dolly",
     path:"/pyements made"
    },
    {
     title:"vendor credits",
     icon:"fas fa-comments-dollar",
     path:"/vendor credits"
    },
   ],
  }
 },
 methods: {

   clickParent(){
    console.log('menusidebar');
    const collapsed = document.body.classList.contains('leftpanel-collapsed');
  
   if(collapsed){
    document.querySelectorAll('.nav-parent').forEach(nav =>{
     nav.addEventListener('click',() => {
      nav.classList.toggle("nav-hover");
     })});
   }
  },
   Current(){
    let el = document.querySelector('.nav-parent.active');
    if(el != null) el.classList.remove("active"); // hadi mohima hiya bach kat7ayad active men nav-parent 
   },
 },
 components:{
  LinkDirect,
  Dropdowns,
 }
}
</script>
<style lang="scss" scoped>
 ul.nav{
  margin-top: 5px;
  width: 100%;
  display: block;
  padding: 5px;
  .margin-top{
   margin-top:20px
  }
 }
</style>