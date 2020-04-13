<template>
   <main class="main">
           
    <div class="container-fluid">
                    
    <div class="card">
                        
    <div class="card-header">
        <h1> GENERADOR</h1>
    </div>

  <div class="card-body" id="test">
  <div class="row">
  <div class="col-md-6  border">
  <div>
      <h3 >QR CODE</h3>
           <label for="num">Numero de paginas</label>
             <div ref="content">
              
               <input v-model.number="count" >
                  
               
                   <table id="testdiv"> 
                     <tr v-for="n in 9" :key="n" >
                       <td v-for="n in 7" :key="n"  >
                  
                  <div class="divqr"    v-for="n in count" :key="n">
                       
             
                 <qrcode :value="randomNumber()" :options="{ width: 100 }" tag="img"  id="qr"></qrcode>
                    
                    
                    
                    </div>
                  </td>
                </tr>
              </table>
               </div>
     
        <button v-print="'#testdiv'" >Print local range</button>
         
            </div>
          </div>
     

                 

                               </div>
                     </div>             
                </div>
            </div>
        </main>  
</template>

<script>

import Vue from 'vue';
import VueQrcode from '@chenfengyuan/vue-qrcode';
import Print from 'vue-print-nb';
import QrcodeVue from 'qrcode.vue'

Vue.component(VueQrcode.name, VueQrcode);
Vue.use(Print);

export default {
     
 methods : {
    randomNumber : function(){
    return Math.random().toString(36).substring(2, 15);

   }
  

  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

table {
  margin: 0 auto;
  
}


</style>
