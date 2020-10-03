
<!DOCTYPE html>

<head>

  <meta charset="UTF-8">
        <link rel="icon" type="image/png" sizes="250x250" href="https://sfmg1234.github.io/MGCounts/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="250x250" href="https://sfmg1234.github.io/MGCounts/favicon-32x32.png">
</head>

<style>





.counter:before {
        background-image: url("./path/to/your/profileimage.png");
    }



body {
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: sans-serif;
  background-color: #FF0000;
  color: #FFF;
  flex-direction: column;
  text-align: center;
}

.bg {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: -1;
  opacity: .25;
  width: 50vmax;
  height: auto;
  filter: blur(3vmax);
}

.avatar {
  width: 10vmax;
  height: 10vmax;
  border-radius: 100%;
  margin-bottom: 2vmax;
}

.subscribers {
  font-size: 10vmax;
}

big {
 font-size: 18px; 
}

small {
  font-size: 14px;
}


body {
        text-align: center
    }

#subs {
  font-size: 50px;
}

#views {
  font-size: 50px;
}

#videoCount {
  font-size: 50px;
}


h1{font-size:90px;}

h1 { color: #FFFFFF; background: linear-gradient sans-serif; }






</style>


<body>
  
  <h1>Subscriber Counter</h1>
  <br>
  <br>
  <br>
 
<link rel=stylesheet href="https://sfmg1234.github.io/MGCounts/odometer-theme-default.css">
<img id="img-bg" class="bg" src="https://yt3.ggpht.com/a-/AOh14GgWNp0Dp7-A6lmaH3vWw3GfhQxNFyAyH1KYqRGnqA=s100-c-k-c0xffffffff-no-rj-mo" width="50" height="50">
<img id="img-avatar" class="avatar" src="https://yt3.ggpht.com/a-/AOh14GgWNp0Dp7-A6lmaH3vWw3GfhQxNFyAyH1KYqRGnqA=s100-c-k-c0xffffffff-no-rj-mo" width="50" height="50">
<br>
<br>
<br>
<div><big id="title">Video</big></div>

<br>
<br>


<div class="info">
  <div class="odometer subs" id="subs">0</div>
  <div><small>Subscribers</small></div>
</div>


<div class="container">
<h2>Total Views</h2>
<div class="odometer" id="views">0</div>
<h2>Channel Videos</h2>
<div class="odometer" id="videoCount">0</div>


<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

<div><big id="description">Description</big></div>



</div><link rel=stylesheet href="https://sfmg1234.github.io/MGCounts/odometer-theme-default.css">

</body>


 <script src="https://sfmg1234.github.io/MGCounts/odometer.js.download"></script>


<script>

var params = new URLSearchParams(document.location.search.substring(1));
var CHANNEL_ID = params.get("id");
//alert(document.location.host);
//alert(CHANNEL_ID);
//var CHANNEL_ID = "UCzsVMzUqVPd9taVz6VGY12g";

const API_KEY = "AIzaSyCpCM4UEHC3ZBuAvAxUw6vJKQBrO9t0jJY";
const API_URL = 'https://www.googleapis.com/youtube/v3/';


var description_url = `${API_URL}channels?part=snippet&id=${CHANNEL_ID}&key=${API_KEY}`;
var subscribers_url = `${API_URL}channels?part=statistics&id=${CHANNEL_ID}&key=${API_KEY}`;
var picture_url = `${API_URL}channels?part=snippet&id=${CHANNEL_ID}&key=${API_KEY}`;
var views_url = `${API_URL}channels?part=statistics&id=${CHANNEL_ID}&key=${API_KEY}`;
var videoCount_url = `${API_URL}channels?part=statistics&id=${CHANNEL_ID}&key=${API_KEY}`;


async function getGubbdescription() {
  const response = await fetch(description_url);
  const data = await response.json();
  const description = data.items[0].snippet.description;
  document.getElementById('description').innerHTML = description;
}

async function getGubbSubs() {
  const response = await fetch(subscribers_url);
  const data = await response.json();
  const subs = data.items[0].statistics.subscriberCount;
  document.getElementById('subs').innerHTML = subs;
}

async function getGubbViews() {
  const response = await fetch(views_url);
  const data = await response.json();
  const views = data.items[0].statistics.viewCount;
  document.getElementById('views').innerHTML = views;
}

async function getGubbvideoCount() {
  const response = await fetch(views_url);
  const data = await response.json();
  const videoCount = data.items[0].statistics.videoCount;
  document.getElementById('videoCount').innerHTML = videoCount;
}

async function getGubbThumb() {
  const response = await fetch(picture_url);
  const data = await response.json();
  const thumb = data.items[0].snippet.thumbnails.medium.url;
  const title = data.items[0].snippet.title;
  document.getElementById('img-bg').src = thumb;
  document.getElementById('img-avatar').src = thumb;
  document.getElementById('title').innerHTML = title;
}





getGubbdescription();
getGubbSubs();
getGubbThumb();
getGubbViews();
getGubbvideoCount();
//yourFunction();



function updatePage(){
    var channel = document.getElementsByName("id").value;
    var your_form = document.getElementById('SUBS_ID');
    your_form.action = document.location.href + '?id=' + channel;
}



</script>



    
    
<br>
<br>
<br>
<br>
<br>

<center><form id = "SUB_ID" onsubmit="updatePage()">
    <input type="text" name="id">
    <input type="submit" value="Count!">
</form></center>
    <br>
    <br>
<h3>Channel ID</h3>





<br>
<br>
<br>
<br>
<br>
<br>
<br>






</html>













<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-177075755-1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-177075755-1');
</script>
