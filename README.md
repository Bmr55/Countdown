# Simple Countdown WebApp

## countdown.js
```js
// Set the date we're counting down to
var countDownDate = new Date("Jan 21, 2021 00:00:00").getTime();

// Update the count down every 1 second
var x = setInterval(function() {

    // Get todays date and time
    var now = new Date().getTime();

    // Find the distance between now an the count down date
    var distance = countDownDate - now;

    // Time calculations for days, hours, minutes and seconds
    var days = Math.floor(distance / (1000 * 60 * 60 * 24));
    var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    var seconds = Math.floor((distance % (1000 * 60)) / 1000);

    // Output the result in an element with id="display"
    document.getElementById("display").innerHTML = days + "d " + hours + "h "
    + minutes + "m " + seconds + "s ";

    // If the count down is over, write some text
    if (distance < 0) {
        clearInterval(x);
        document.getElementById("display").innerHTML = "EXPIRED";
    }
}, 1000);
```
## index.html
```html
<html>
<head>
  <!-- Fonts -->
  <link href="https://fonts.googleapis.com/css?family=Righteous" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css?family=Rubik+Mono+One" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css?family=Carrois+Gothic+SC" rel="stylesheet">
  
  <!-- Main Stylesheet -->
  <link href="css/styles.css" type="text/css" rel="stylesheet">

</head>
<body>

  <h1>Countdown</h1>

  <!-- Element where text will be updated --> 
  <p id="display"></p>
  
  <h2>Remaining</h2>
  
  <!-- Include JS Script -->
  <script type="text/javascript" src="js/countdown.js"</script>
</body>
</html>
```
