
<!DOCTYPE html>
<html>
    <head>
     <meta charset="UTF-8">



     <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/odometer.js/0.4.8/themes/odometer-theme-default.min.css">
     <title>VS</title>
    </head>
    <body>

      <style>

body {
  text-align: center;
  font-family: Roboto;
  background-color: white
}

          .container {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        flex: 3;
        margin-bottom: 10%
    }


#clicks {
  font-size: 80px;
}

#subs {
  font-size: 80px;
}

#SubGap {
  font-size: 80px;
}

 #rate2 {
  font-size: 40px;
}

#rate1 {
  font-size: 40px;
}

#rate {
  font-size: 40px;
}

#rate3 {
  font-size: 40px;
}

 #rate4 {
  font-size: 40px;
}

#rate5 {
  font-size: 40px;
}

 #rate6 {
  font-size: 40px;
}

#rate7 {
  font-size: 40px;
}

#rate8 {
  font-size: 40px;
}


 img {
    border-radius: 50%;
  }

#img {
    border: solid .5vh !Important;
    border-radius: 100%;
    border-color: rgb(79, 79, 79) !Important;
}

 </style>


<div class="container">
<div>



<img class="img-fluid border rounded-circle shadow image" style="width: 150px;height: 150px;" src="https://yt3.ggpht.com/a/AATXAJzOcyc2UwB0vlV7SyfzwgU_La1FOFZmObW3HCH0VzM=s88-c-k-c0x00ffffff-no-rj">
<h2 id="username">T-Series</h2>
<div id="subs" class="odometer">0</div>
</div>



<div>
<img class="img-fluid border rounded-circle shadow image2" style="width: 150px;height: 150px;" src="https://bestanimations.com/Earth&Space/Earth/earthglobeanimation/globe-earth-animation-15-2.gif">
<h2 id="username2">Global Clicker</h2>
<div id="clicks" class="odometer">0</div>
</div>
</div>        




         <div class="container">
<div>



<h4 class="title" id="ViewLabel" >Avg Clicks Per Second</h4>
<div class="odometer" id="rate3">0</div>



</div>
<div>



<h4 class="title" id="ViewLabel" >Avg Clicks Per Minute</h4>
<div class="odometer" id="rate4">0</div>




</div>
<div>

<h4 class="title" id="ViewLabel" >Avg Clicks Per Hour</h4>
<div class="odometer" id="rate5">0</div>

</div>





<div>



<h4 class="title" id="ViewLabel" >Avg Clicks Per Second</h4>
<div class="odometer" id="rate">0</div>



</div>
<div>



<h4 class="title" id="ViewLabel" >Avg Clicks Per Minute</h4>
<div class="odometer" id="rate1">0</div>




</div>
<div>

<h4 class="title" id="ViewLabel" >Avg Clicks Per Hour</h4>
<div class="odometer" id="rate2">0</div>

</div>
</div> 




        <div>Gap</div>
        <div class="odometer" id="SubGap">0</div>

                 <br>
                 <br>
                 <br>

</div> 

      <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/odometer.js/0.4.8/odometer.min.js"></script>
      <script>


 var avg = [];
 var avg2 = [];
 var avg3 = [];    

        var count1 = 0; //sub count from 1st channel
        var count2 = 0; //sub count form 2nd channel






       async function getSFStat() {
        let request = await fetch('https://api.allorigins.win/raw?url=http://global-clicker.mrcode.io/getpoints', { mode: "cors" })
        let data = await request.json().catch(() => {})
        if (!data) return;
        clicks.innerHTML = data
        count2 = data

        avg.push (data)
        if (avg.length >= 60000) {avg.shift()}
        var count = 0;
        for(var i = 0; i < avg.length;i++) {
          if(i == 0) {
            count = count + (avg[i] - parseFloat(avg[i]))
          } else {
            count = count + (parseFloat(avg[i]) - parseFloat(avg[i-1]))
          }
        }
        var deta = count/avg.length 
        rate.innerHTML = Math.floor(deta)
       rate1.innerHTML = Math.floor(deta*60)
     rate2.innerHTML = Math.floor(deta*3600)




     }
    setInterval(getSFStat, 3000)
    getSFStat()



async function getSFStats() {
        let request = await fetch('https://api.allorigins.win/raw?url=https://mixerno.space/api/youtube/estimated/user/UCq-Fj5jknLsUf-MWSy4_brA', { mode: "cors" })
        let data = await request.json().catch(() => {})
        if (!data) return;
        subs.innerHTML = Math.floor(data.SubscriberCount)
        count1 = Math.floor(data.SubscriberCount)
       SubGap.innerHTML = count1-count2;
       avg2.push (data.SubscriberCount)
        if (avg2.length >= 60000) {avg2.shift()}
        var count = 0;
        for(var i = 0; i < avg2.length;i++) {
          if(i == 0) {
            count = count + (avg2[i] - parseFloat(avg2[i]))
          } else {
            count = count + (parseFloat(avg2[i]) - parseFloat(avg2[i-1]))
          }
        }
        var deta = count/avg2.length 
        rate3.innerHTML = Math.floor(deta)
       rate4.innerHTML = Math.floor(deta*60)
     rate5.innerHTML = Math.floor(deta*3600)


     }
    setInterval(getSFStats, 3000)
    getSFStats()    


 async function getSFStatss() {
        let request = await fetch('https://api.allorigins.win/raw?url=https://mixerno.space/api/youtube/estimated/user/UCq-Fj5jknLsUf-MWSy4_brA', { mode: "cors" })
        let data = await request.json().catch(() => {})
        if (!data) return;

       SubGap.innerHTML = count1-count2;
       avg3.push (count1-count2)
        if (avg2.length >= 60000) {avg2.shift()}
        var count = 0;
        for(var i = 0; i < avg2.length;i++) {
          if(i == 0) {
            count = count + (avg2[i] - parseFloat(avg2[i]))
          } else {
            count = count + (parseFloat(avg2[i]) - parseFloat(avg2[i-1]))
          }
        }
        var deta = count/avg2.length 
        rate6.innerHTML = Math.floor(deta)
       rate7.innerHTML = Math.floor(deta*60)
     rate8.innerHTML = Math.floor(deta*3600)


     }
    setInterval(getSFStatss, 3000)
    getSFStatss()    


 //yourFunction();



         var params = location.href.split('&id=');
        var channel_id = params[1];
        var channel_id2 = params[2];
        var count1 = 0;
        var count2 = 0;






     </script>
    <br>
    <br>
        <br>
            <br>
                <br>

    </body>
</html>
