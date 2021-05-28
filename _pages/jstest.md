---
permalink: /jstest/
title: JS Test Page
---

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eu lacinia magna, non condimentum felis. Praesent ac nibh nec magna porttitor tincidunt. Sed bibendum purus magna, vel dictum enim commodo ac. Ut non metus mi. Fusce volutpat accumsan metus, volutpat pellentesque odio tincidunt quis. Sed pellentesque eleifend enim sit amet maximus. Cras auctor posuere ipsum sit amet lobortis. Duis mattis ullamcorper malesuada. Nunc ex nisi, efficitur id faucibus vel, finibus vel leo. Donec sodales turpis vel dolor interdum fringilla. Fusce efficitur varius tellus at gravida. Cras at venenatis felis, a pellentesque sem.


<div id="clock">8:10:45</div>
<script>
    setInterval(showTime, 1000);
    function showTime() {
        let time = new Date();
        let hour = time.getHours();
        let min = time.getMinutes();
        let sec = time.getSeconds();
        am_pm = "AM";

        if (hour > 12) {
            hour -= 12;
            am_pm = "PM";
        }
        if (hour == 0) {
            hr = 12;
            am_pm = "AM";
        }

        hour = hour < 10 ? "0" + hour : hour;
        min = min < 10 ? "0" + min : min;
        sec = sec < 10 ? "0" + sec : sec;

        let currentTime = hour + ":" 
            + min + ":" + sec + am_pm;

        document.getElementById("clock")
            .innerHTML = currentTime;
    }

    showTime();
</script>
