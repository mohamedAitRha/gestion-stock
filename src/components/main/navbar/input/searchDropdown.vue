<template>
 <div class="inputSearch">
    <span @click="open = (open)? false : true">
     <i class="fas fa-search"></i>
     <i class="fas fa-caret-down"></i>
    </span>
     <input class="form-control" type="search" :placeholder="'search '+search">
     <ul class="listSearch" :class="{'show-list':open}">
      <li>
       <a @click="search='in customer';open=!open">
        <i :class="{'fas fa-check':search === 'in customer'}"></i>
        <div class="choix">customer</div>
       </a>
      </li>
      <li>
        <a @click="search='in vendors';open=!open">
        <i :class="{'fas fa-check':search === 'in vendors'}"></i>
        <div class="choix">vendors</div>
       </a>
      </li>
      <li>
       <a @click="search='in invoices';open=!open">
        <i :class="{'fas fa-check':search === 'in invoices'}"></i>
        <div class="choix">invoices</div>
       </a>
      </li>
      <li class="last">
       <a class="padding-left">
        <div class="choix">
         <i class="fas fa-search"></i>
         advance search
        </div>
       </a>
      </li>
     </ul>
   </div>
</template>

<script>
export default {
 data() {
  return {
   open:false,
   search:''
  }
 },
}
</script>

<style lang="scss" scoped>
  
@import '@/global/css/_global-variable.scss';

  .inputSearch:hover,.inputSearch:focus-within{
     border: 1px solid $BordercolorBlue;
    }
     .inputSearch{
      position: relative;
      display: flex;
      justify-content: center;
      border-radius: 20px;
      padding:0 2px;
      border: 1px solid #eee;
      height: 33px;
      align-items: center;
      background: #fff;
      flex-grow: 1;
      i{
       font-size: .9rem;
      }
      
      >span{
       :active{
        transform: scale(.95);
       }
       >i:last-child{
        font-size: .7rem;
       }
       padding:0 10px;
       display: flex;
       justify-content: space-between;
       align-items: center;
       width: 50px;
       cursor: pointer;
      }
     
      input,input:focus{
       box-shadow: none;
       border: none;
       background: none;
       outline: none;
       flex-grow: 2;
       width: auto;
       padding: 2px 5px 2px 0;
       font-size: .8rem;
      }
      ::-webkit-input-placeholder {
       text-transform: capitalize;
       font-size: .9rem;
       }
        
        :-moz-placeholder { 
           text-transform: capitalize;
        }
        
        ::-moz-placeholder {  
           text-transform: capitalize;
        }
        
        :-ms-input-placeholder { 
           text-transform: capitalize;
        }

        ul.listSearch.show-list{
         padding: 7px 0 0;
         max-height: 500px;
         transition: max-height .25s,padding .25s .25s ease-in-out;
         border: 1px solid #eee;

        }

        ul.listSearch{
         overflow: hidden;
         width: 100%;
         border-radius: 4px;
         list-style: none;
         margin: 0;
         position: absolute;
         top: 105%;
         left: 0;
         padding:0;
         max-height: 0px;
         background-color: #fff;
         transition: max-height .15s,padding .15s .15s ease-in;
         li{
          height:28px;
          :hover,:focus{
           background-color: $backgroudBlue;
           color: #fff;
           i{
            color: #fff;
           }
          }
          a:active{
           outline: none;
          }
          a{
           cursor: pointer;
           display: flex;
           width: 100%;
           height: 100%;
           align-items: center;
           background-color: #fff;
           border: none;
           i{
            padding: 7px;
            font-size: .9rem;
            width: 28.4px;
           }
           .choix{
            flex-grow: 2;
            text-align: left;
            padding: 0 5px;
           }
          }
         }
         li.last:hover,:focus{
          background-color: $mainBackgroud;
          color: $BordercolorBlue;
          :hover,:focus{
            background-color: $mainBackgroud;
            color: $BordercolorBlue;
           }
         }
         li.last{
          height: 45px;
          
          a.padding-left{
           padding-left: 22px;
           color: $BordercolorBlue;
           border:0px solid #eee;
           border-width: 1px 0px 0 ;
           i{
            color: $BordercolorBlue ;
           }
          }
         }
        }
    }
</style>