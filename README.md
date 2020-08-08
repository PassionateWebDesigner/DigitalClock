<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body{
            background-color: black;
        }
        p{
            font-size:70px;
            color:skyblue;
            position: absolute;
            top:15%;
            left:30%;
        }
        .clock{
            position: absolute;
            top:50%;
            left:50%;
            transform: translateX(-50%) translateY(-50%);
            color: skyblue;
            font-size: 30px;
            border: 1px dashed #ccc;
            padding:0 10px 0 10px;
        }
        @media (min-width:768px){
            .clock{
                font-size:130px;
            }
        }
        @media (max-width: 768px){
            p{
                top:35%;
                left:10%;
                font-size:30px;
            }
        }
    </style>
</head>
<body>
    <p>Your Time Starts Now</p>
    <div id="clockdisplay" class="clock"></div>
    <script type="text/javascript">
       function showTime(){
           var d = new Date();
           var hrs = d.getHours();
           var min= d.getMinutes();
           var sec=d.getSeconds();
           var session= "AM";

           if(hrs == 0){
               hrs = 12;
           }
           if(hrs > 12){
               hrs = hrs - 12;
               session = "PM";
           }
           hrs = (hrs < 10) ? "0" + hrs : hrs;
           min = (min < 10) ? "0" + min : min;
           sec = (sec < 10) ? "0" + sec : sec;

           var time = hrs + ":" + min + ":" + sec +" " + session;
           document.getElementById("clockdisplay").innerText = time;
           document.getElementById("clockdisplay").textContent = time;

           setTimeout(showTime,1000);
       }     
       showTime(); 
    </script>
</body>
</html>
