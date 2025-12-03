# MANUFACTURER COUPON
(FOR VENDORS USE ONLY)
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Coupon Countdown</title>
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">

<style>
    body {
        margin: 0;
        background: #0f6a36;
        font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Arial;
        color: white;
        height: 100vh;
        overflow-x: hidden;
    }

    .wrapper {
        max-width: 500px;
        margin: auto;
        padding: 20px;
        text-align: center;
    }

    h1 {
        font-size: 22px;
        margin-bottom: 20px;
        font-weight: 600;
    }

    .coupon-box {
        background: white;
        border-radius: 18px;
        overflow: hidden;
        box-shadow: 0 10px 30px rgba(0,0,0,0.28);
    }

    .coupon-box img {
        width: 100%;
        display: block;
    }

    .timer-section {
        padding: 18px;
        background: #ffffff;
        color: #0f6a36;
        font-weight: bold;
        font-size: 42px;
        letter-spacing: 1px;
    }

    .footer-text {
        margin-top: 14px;
        font-size: 12px;
        opacity: .85;
        line-height: 1.4;
    }
</style>

</head>
<body>

<div class="wrapper">

    <h1>Your Coupon</h1>

    <div class="coupon-box">
        <img src="844551A2-F653-4701-98C0-6E84A9240276.jpeg" alt="Coupon Image">
        <div class="timer-section" id="countdown">05:00</div>
    </div>

    <div class="footer-text">
        This countdown resets each time you reload the page.<br>
        For demo/mockup use only.
    </div>

</div>

<script>
    // 5-minute countdown
    let time = 5 * 60;
    const countdownEl = document.getElementById("countdown");

    function updateTimer() {
        let minutes = Math.floor(time / 60);
        let seconds = time % 60;

        minutes = minutes < 10 ? "0" + minutes : minutes;
        seconds = seconds < 10 ? "0" + seconds : seconds;

        countdownEl.textContent = `${minutes}:${seconds}`;

        if (time > 0) {
            time--;
        } else {
            countdownEl.textContent = "EXPIRED";
            clearInterval(timerInterval);
        }
    }

    let timerInterval = setInterval(updateTimer, 1000);
</script>

</body>
</html>
