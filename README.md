# effective-memory
<html>
<head>
    <title>Get fit</title>
    <style>
        #dashboard{
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: darksalmon;
            padding: 20px;
            font-family: sans-serif ;

        }
       
    </style>

<script type="text/javascript"> 

      var startTime;
      var elapsedTime = 0;
      var timerInterval;

      function startstopwatch(){
        startTime = Date.now() -elapsedTime;
        timerInterval = setInterval(updateSrtopwatch, 10);
        document.getElementById("startBtn").disabled = true;
        document.getElementById("stopBtn").disabled =true;
      }

      function stopstopwatch(){
        clearInterval(timerInterval);
        elapsedTime = 0;
        document.getElementById("timer").textContent = "00:00:00:000";
        document.getElementById("startBtn").disabled = false;
        document.getElementById("stopBtn").disabled = false;
      }

      function updateStopwatch(){
        var currentTime = Date.now();
        elapsedTime = currentTime -startTime;

        var minutes = Math.floor(elapsedTime/60000);
        var seconds = Math.floor((elapsedTime - minutes * 60000)/1000);
        var milliseconds = Math.floor((elapsedTime - minutes * 60000 - seconds * 1000)/10);

       if (minutes < 10)minutes ="0" + minutes;
       if (seconds < 10)seconds ="0" + seconds;
       if(milliseconds < 10) milliseconds = "0" + milliseconds;

       document.getElementById("timer").textContent = minutes + ":" + seconds + ":" + milliseconds;


}

function display_c(){
var refresh=1000; // Refresh rate in milli seconds
mytime=setTimeout('display_ct()',refresh)
}

function display_ct() {
var x = new Date()
document.getElementById('ct').innerHTML = x;
display_c();
 }



</script>
</head>

<body onload=display_ct(); style="background-color: bisque;">
    <h1  style="text-align: center;">Heeey peeeps!</h1>

    <div id="dashboard">
      <span id='ct' ></span>
    </div><br>

    <div id="timer">00:00:00:000</div><br>
    <button id="startBtn" Onclick="startstopwatch()">Start</button>
    <button id="stoptBtn" Onclick="stopstopwatch()">Stop</button>
    <button id="resetBtn" Onclick="resttstopwatch()">Reset</button>



</body>
</html>
