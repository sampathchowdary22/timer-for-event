# timer-for-event
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>New Year Countdown Timer</title>
<style>
    body {
        font-family: Arial, sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #f0f0f0;
        margin: 0;
        background-image: url(newyear.png);
        background-repeat:no-repeat ;
        background-size:cover ;
    }

    .countdown-container {
        text-align: center;
    }

    h1 {
        color: whitesmoke;
    }

    #countdown {
        font-size: 2rem;
        color: whitesmoke;
        margin-top: 20px;
    }
</style>
</head>
<body>
<div class="countdown-container">
    <h1>New Year Countdown</h1>
    <div id="countdown"></div>
</div>

<script>
    document.addEventListener('DOMContentLoaded', function() {
        // Set the date we're counting down to
        var countDownDate = new Date("Jan 1, 2025 00:00:00").getTime();

        // Update the countdown every second
        var countdownFunction = setInterval(function() {

            // Get the current date and time
            var now = new Date().getTime();

            // Find the distance between now and the countdown date
            var distance = countDownDate - now;

            // Time calculations for days, hours, minutes and seconds
            var days = Math.floor(distance / (1000 * 60 * 60 * 24));
            var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            var seconds = Math.floor((distance % (1000 * 60)) / 1000);

            // Display the result in the element with id="countdown"
            document.getElementById("countdown").innerHTML = days + "d " + hours + "h "
                + minutes + "m " + seconds + "s ";

            // If the countdown is finished, show text
            if (distance < 0) {
                clearInterval(countdownFunction);
                document.getElementById("countdown").innerHTML = "Happy New Year!";
            }
        }, 1000); // Update every 1 second
    });
</script>
</body>
</html>
