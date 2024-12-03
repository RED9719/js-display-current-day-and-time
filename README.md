# js-display-current-day-and-time

Write a JavaScript program to display the current day and time.
CODE
<!DOCTYPE html>
<html>
<head>
    <title>Current Day and Time</title>
    <script>
        function showDateTime() {
            var now = new Date();
            var days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
            var day = days[now.getDay()];
            var hours = now.getHours();
            var minutes = now.getMinutes();
            var seconds = now.getSeconds();
            var ampm = hours >= 12 ? 'PM' : 'AM';
            hours = hours % 12;
            hours = hours ? hours : 12; // the hour '0' should be '12'
            minutes = minutes < 10 ? '0' + minutes : minutes;
            seconds = seconds < 10 ? '0' + seconds : seconds;
            var strTime = hours + ':' + minutes + ':' + seconds + ' ' + ampm;
            document.getElementById("day-time").innerHTML = "Today is " + day + ". Current time is " + strTime + ".";
        }
        setInterval(showDateTime, 1000); // Refresh every second
    </script>
</head>
<body onload="showDateTime()">
    <h1>Current Day and Time</h1>
    <p id="day-time"></p>
</body>
</html>
