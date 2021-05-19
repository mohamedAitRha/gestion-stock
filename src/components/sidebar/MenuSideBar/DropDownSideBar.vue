<template>

   <li class="nav-parent" @click="navClick">
    <a class="nav" :class="{'nav-active':show}">
     <i :class="icon"></i> 
     <span>
       <div class="title">
        {{title}}
       </div>
     </span>
     <i class="fas fa-chevron-up iconRight" :class="{'rotate':show}"></i>
    </a>
    <ul :class="{'showList':show}" class="children">
      <router-link @click.native="activeToggle" v-for="child,indexChild in children" :key="indexChild" :to="child.to" tag="li">
       <a class="link"><i class="fa fa-caret-right"></i> {{child.childText}}</a>
      </router-link>
    </ul>
   </li>
 
</template>

<script>
export default {
 name:"DropDownSideBar",
 props:["title","icon","children"],
 data(){
  return{
   show:false,
   hover:false,
  }
 },
 methods: {

   mouseEnter(e){
     let el = document.body.classList.contains('leftpanel-collapsed');
     if(el){
      if(e.target.tagName === 'A' && e.target.className === "nav") e.target.parentElement.classList.add("nav-hover");
      if(e.target.tagName === 'I' || e.target.tagName === 'SPAN') e.target.parentElement.parentElement.classList.add("nav-hover");
      console.log(e.target.tagName +", enter");
      this.show = true;
      }
      
   },
   mouseLeave(e){
     console.log("pas encor");
     let el = e.target.parentElement.classList.contains('nav-hover');
     if(el){
      if(e.target.className === 'children') {
       e.target.parentElement.classList.remove("nav-hover");
       console.log(e.target.tagName +", OUT");
       this.show = false;
       }
      }
   },

  activeToggle(){
   let el = document.querySelector('.nav-parent.active');

     document.querySelector(".router-link-exact-active.router-link-active").parentElement.parentElement.classList.add("active");
     if(el != null && document.querySelector(".router-link-exact-active.router-link-active").parentElement.parentElement != el) 
     el.classList.remove("active");   
  },
  navClick(){ 
    let el = document.body.classList.contains('leftpanel-collapsed');
    if(!el)
    this.show = (this.show)? false : true;
  },
  eventLoad(v){
    console.log("run");
    if(v){
      
      document.querySelectorAll(".nav-parent").forEach(ele => {
      ele.addEventListener("mouseover",()=>{ele.classList.add("nav-hover");});
      ele.addEventListener("mouseout",()=>{ele.classList.remove("nav-hover");});
     })
    }
    else{
     console.log("run1")
      document.querySelectorAll(".nav-parent").forEach(ele => {
      ele.addEventListener("click",()=>{
       ele.querySelector("ul.children").classList.toggle("d-none");
      });
     })
    }
  }
 },
}
</script>

<style lang="scss" scoped>
@import '@/global/css/_global-variable.scss';
//*************NAV PARENT *******/
.nav-parent{
 cursor: pointer;
 margin-bottom: 2px;
 position: relative;

.router-link-exact-active.router-link-active{
  a{i:first-of-type{color: $colorActive;}}
}
.iconRight
{
    font-size: 9px !important;
    margin-right: 10px !important;
    position: absolute;
    right: 3px;
    transform: rotate(90deg);
    transition: transform .15s;
}
.iconRight.rotate
{
    transform: rotateZ(180deg);
}
//STAYLING LINK
    a.nav:hover,a.nav.nav-active{
    background-color:$colorActive;
    color: $colorSidebar !important;
    box-shadow: 0 3px 0 #00000033;
 }
  a.nav{
   color: $colorSidebar;
   padding: 7px 10px;
   text-decoration: none;
   display: flex;
   align-items: center;
   position: relative;
   border-radius: 4px;
   font-size: 13px;

   i:first-of-type {
     font-size: 16px;
     vertical-align: middle;
     margin-right: 12px;
     width: 16px;
     display: flex;
     justify-content: center;
     align-items: center;
     color:$colorSidebar;
   }
}
// END STYLING LINK

// UL CHILDREN STYLE
.children.showList{
 max-height: 500px;
transition: max-height 0.25s .15s ease-in;
}

.children
 {
  transition: max-height 0.15s ease-out;
  overflow: hidden;
  list-style: none;
  margin: 2px 0;
  padding: 0;
  max-height: 0;
  li{
   :hover,:focus,:active{
        text-decoration: none;
        color: $colorActive;
   }
   a{
    color: $colorSidebar;
    font-size: 13px;
    display: flex;
    padding: 5px 0 5px 27px;
    -webkit-transition: all 0.2s ease-out 0s;
    transition: all 0.2s ease-out 0s;
    align-items:center;
   }
   .fa {
    font-size: 12px;
    opacity: 0.5;
    margin-right: 10px;
    text-align: left;
    width: auto;
    vertical-align: baseline;
      }
   }
 }
 // END STYLE CHILDREN

   
}

//************* NAV PARENT ACTIVE *******/
.nav-parent.active{
   
   a.nav{ background-color: $backgroundActive !important;
    color: $colorActive !important;
    >i:first-of-type{
     color: $colorActive;
    }
    }
}


//*************LEFT PANEL COLLAPSED *******/

.leftpanel-collapsed .nav-parent{

 //transition: all .15s ease-in;

 a.nav{
   padding: 10px;
   box-shadow: none;
   justify-content: center;
  .iconRight{
   display: none;
  }
  span{
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
    transition: all 0.15s ease-out;
    div.title{
       display: flex;
       align-items: center;
       height: 36px;
       color:transparent;
    }
  }
  >i:first-of-type { margin-right: 0px; }
 }
 ul.children{
  transition: min-height 0.15s ease-out;
  position: absolute;
  top: 36px;
  left: 45px;
  overflow: hidden;
  list-style: none;
  padding: 0;
  max-height: 0;
  min-width: 0;
  i{
   margin-right: 10px;
  }
 }
}

//************* NAV PARENT IN ACTIVE HOVER **********************/
.leftpanel-collapsed .nav-parent.active:hover{
  background-color: $backgroundActive !important;
 a.nav{ 
  >span{
   background-color: $backgroundActive !important;
   padding-left: 20px;
   min-height: 36px;
   min-width: 214px;
   transition: all 0.15s ease-in;
   div.title{color:$colorActive !important;}
  }
  }
}
//*************NAV PARENT HOVER *******/
.leftpanel-collapsed .nav-parent:hover{
 background-color: $colorActive ;
 border-radius:4px 0px 0px 4px ;
 a.nav{
  background-color: $colorActive ;
  color: $colorSidebar ;
  span{
    //display: flex !important;
    //align-items: center;
    background-color: $colorActive;
    border-radius:0px 4px 0px 0px;
    padding-left: 20px;
    min-height: 36px;
    min-width: 214px;
    transition: all 0.15s ease-in;
    div.title{color:$colorSidebar;}
  }
 }
 ul.children {
    /*position: absolute;
    top: 36px;
    left: 45px;*/
    margin: 0;
    min-width: 204px;
    background: #1d2939;
    z-index: 100;
    border-radius: 0 0 2px 0;
    max-height: 500px;
    transition: max-height 0.25s .15s ease-in;
  }
}



</style>