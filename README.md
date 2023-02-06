# Analog_Clock
analog clock code using html,css and Javascript 

<!DOCTYPE html>
<html>
<head>
<style>
#clock {
   width: 300px;
   height: 300px;
   margin: 0 auto;
   padding: 10px;
   border: 1px solid #333;
   background: #f1f1f1;
   position: relative;
}
#sec, #min, #hour {
   position: absolute;
   width: 40%;
   height: 6px;
   top: 47%;
   left: 30%;
   margin-top: -104px;
   margin-left: -104px;
   background: #333;
   border-radius: 50%;
   z-index: 5;
}
#sec {
   transform: rotate(90deg);
   animation: rota 6s linear infinite;
}
#min {
   transform: rotate(90deg);
   animation: rota 60s linear infinite;
}
#hour {
   transform: rotate(90deg);
   animation: rota 3600s linear infinite;
}
@keyframes rota {
   100% { transform: rotate(360deg); }
}
</style>
</head>
<body>

<div id="clock">
  <div id="sec"></div>
  <div id="min"></div>
  <div id="hour"></div>
</div>

<script>
// Get the current time
var date = new Date();
var hour = date.getHours();
var min = date.getMinutes();
var sec = date.getSeconds();

// Calculate the angles of the hands
var hourAngle = (360/12)*hour + (360/(12*60))*min;
var minAngle = (360/60)*min;
var secAngle = (360/60)*sec;

// Rotate the hands
document.getElementById("sec").style.transform = "rotate(" + secAngle + "deg)";
document.getElementById("min").style.transform = "rotate(" + minAngle + "deg)";
document.getElementById("hour").style.transform = "rotate(" + hourAngle + "deg)";
</script>

</body>
</html>
