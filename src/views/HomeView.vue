<template>
  <div class="container">
    <div class="row">
      <!-- Card 1 -->
      <div class="card1">
        <div class="card1-head" >         
          <h4 style="text-align: center; margin: 2%;" ><strong>💵ยอดขาย</strong></h4>          
        </div>
        <hr>
        <div class="card1-content">
          <p style="text-align: center; margin: 5%;" ><b>{{ income }} บาท</b></p>
          <p style="text-align: left; margin: 5%;" >ดูรายละเอียดเพิ่มเติม</p>
        </div>
      </div>
      <!-- card 2  -->
      <div class="card2">
        <div class="card2-head">
          <h4 style="text-align: center; margin: 2%;" ><strong>🛒จำนวนที่ขาย</strong></h4>
          <hr>
        </div>
        <div class="card2-content">
          <p style="text-align: center; margin: 5%;" ><b>{{ amount }} ชิ้น</b></p>
          <p style="text-align: left; margin: 5%;" >ดูรายละเอียดเพิ่มเติม</p>
        </div>
      </div>
      <!-- Card 3 -->
      <div class="card3">
        <div class="card3-head">
          <h4 style="text-align: center; margin: 2%;" ><strong>🪙ส่วนลด</strong></h4>
          <hr>
        </div>
        <div class="card3-content">
          <p style="text-align: center; margin: 5%;" ><b>{{discount}} บาท</b></p>
          <p style="text-align: left; margin: 5%;" >ดูรายละเอียดเพิ่มเติม</p>
        </div>
      </div>
      <!-- Card 4 -->
      <div class="card4">
        <div class="card4-head">
          <h4 style="text-align: center; margin: 2%;" ><strong>🎯ยอดขายทั้งเดือน</strong></h4>
          <hr>
        </div>
        <div class="card4-content">
          <p style="text-align: center; margin: 5%;" ><b>{{ totalincome }} บาท</b></p>
          <p style="text-align: left; margin: 5%;" >รายการขาย 387 รายการ</p>
        </div>
      </div>
    </div>
    <!-- Row 2 -->
    <div class="row">
      <div class="topseller">
        <div class="tophead">
          <h4 style="margin: 2%; text-align: center; "><strong>รายการขายประจำวัน</strong></h4>
          <hr>     
        </div>
        <div class="listmenu">
          <ul>
            <li>มะพร้าวปั่นนมสด  24 รายการ</li>
            <li>นมหมีปั่น 15 รายการ</li>
            <li>นมหมีปั่นสตอเบอรี่ 8 รายการ</li>
            <li>นมหมีปั่นคาราเมล 7 รายการ</li>
            <li>นมหมีปั่นปีโป้ 4 รายการ</li>                        
          </ul> 
        </div>
      </div>
      <div class="charts-seller">
        
        <table class="charts-css column">
          <tbody>
            <tr>
              <td style="--size: calc( 15 / 58 )"> นมหมีปั่น </td>
            </tr>
            <tr>
              <td style="--size: calc( 8 / 58 )"> นมหมีปั่นสตอเบอรี่ </td>
            </tr>
            <tr>
              <td style="--size: calc( 7 / 58 )"> นมหมีปั่นคาราเมล </td>
            </tr>
            <tr>
              <td style="--size: calc( 24 / 58 )"> มะพร้าวปั่นนมสด </td>
            </tr>
            <tr>
              <td style="--size: calc( 4 / 58 )"> นมหมีปั่นปีโป้ </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
    <div class="row">
      <div class="logupdate">
        <div class="headlog" style="text-align: left; padding-top: 1%;" ><strong>Update:</strong></div>       
          <div class="marquee">
            <span class="marquee-text" v-for="item in textlog" :key="item.id" >
              {{ textlog.text }}
            </span>
          </div>
      </div>
    </div>
  </div> 
</template>

<script>
import axios from 'axios';

export default {
  data(){
    return {
      logupdate: [],
      income: 1800,
      amount: 58,
      discount: 20,
      totalincome: 15500,
      textlog: {
        id: 1,
        text: '15.32 Joe: ขายมะพร้าวปั่นนมสด 1 ราย  ',
        id: 2,
        text: '15.52 Joe: ขายหมหมี 1 ราย  '
      }
    };
  },
  mounted(){
    
  }, 
  methods: {
    
  }

}
</script>

<style>

.marquee {
  width: 100%;
  white-space: nowrap;
  overflow: hidden;
  position: relative;
}

.marquee-text {
  display: inline-block;
  animation: marquee 20s linear infinite;
}

@keyframes marquee {
  0% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(100%);
  }
}

/* @media (max-width:800px){
  .card1 .card2 .card3 .card4{
    display: flex;
    position: relative;
    min-height: 100vh;
    align-items: center;
    flex: 1;
    max-width: 300px;
  }
} */

 @media (max-width: 860px) {
  .row {
   /*  min-height: 100vh; */
    display: flex;
    align-items: center;
    
    flex: 1;
    max-width: 760px;
    font-size: 50%;
  }
} 

.logupdate {
  background: rgb(255, 255, 255);
  position: relative;
  flex: 1;
  max-width: 1265px;
  height: 150;
  border-radius: 10px;
  border-left: 10px solid red;
  margin-top: 25px ;
}

.charts-seller {
  background: rgb(255, 255, 255);
  position: relative;
  flex: 1;
  max-width: 780px;
  height: 400px;
  margin: 1.2%;
  margin-top: 35px ;
  border-radius: 10px;
  /* box-shadow: 0px 0px 5px rgb(173, 173, 173); */
  /* border: 5px solid aquamarine; */
  padding-bottom: 2%;
}

.topseller {
  background: rgb(255, 255, 255);
  position: relative;
  flex: 0.5;
  max-width: 780px;
  height: 400px;
  margin: 1.2%;
  margin-top: 35px ;
  border-radius: 10px;
  /* box-shadow: 0px 0px 5px rgb(173, 173, 173); */
  border-top: 40px solid orangered;
}
.row{
  width: 100%;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}


.card1{
  background: rgb(255, 255, 255);
  position: relative;
  flex: 1;
  max-width: 300px;
  height: 150px;
  margin: 10px;
  border-radius: 10px;
  /* box-shadow: 0px 0px 5px rgb(173, 173, 173); */
  border-top: 10px solid orangered;
  
}

.card2{
  background: rgb(255, 255, 255);
  position: relative;
  flex: 1;
  max-width: 300px;
  height: 150px;
  margin: 10px;
  border-radius: 10px;
  /* box-shadow: 0px 0px 5px rgb(173, 173, 173); */
  border-top: 10px solid orangered;
}

.card3{
  background: rgb(255, 255, 255);
  position: relative;
  flex: 1;
  max-width: 300px;
  height: 150px;
  margin: 10px;
  border-radius: 10px;
  /* box-shadow: 0px 0px 5px rgb(173, 173, 173); */
  border-top: 10px solid orangered;
}

.card4{
  background: rgb(255, 255, 255);
  position: relative;
  flex: 1;
  max-width: 300px;
  height: 150px;
  margin: 10px;
  border-radius: 10px;
  /* box-shadow: 0px 0px 5px rgb(173, 173, 173); */
  border-top: 10px solid orangered;
}



/*@media (min-width: 1024px) {
  .homecss {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

@media (max-width: 1023px) {
  .homecss {
    min-height: 100vh;
    display: grid;
    align-items: center;
  }
}*/


</style>