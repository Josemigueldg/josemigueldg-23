#josemigueldg23


<!DOCTYPE html>
<html>
<head>
<title>BNB Galaxy V1</title>
<style type="text/css">
body {
background-color: #1F1C2C;
background-image: url("stars.gif");
background-repeat: repeat;
color: #FFFFFF;
font-family: 'Galaxy', sans-serif;
} 

h1 {
font-size: 60px;
margin: 0;
padding: 20px;
text-align: center;
} 

h2 {
font-size: 36px;
margin: 40px 0 20px 0;
padding: 0;
text-align: center;
} 

.container {
margin: 0 auto;
max-width: 800px;
text-align: center;
} 

.btn {
background-color: #1CA1F2;
border: none;
border-radius: 5px;
color: #FFFFFF;
cursor: pointer;
font-size: 18px;
margin: 20px 10px;
padding: 10px 20px;
text-align: center;
text-decoration: none;
transition: background-color 0.3s ease;
} 

.btn:hover {
background-color: #0F5A8C;
} 

.form {
margin: 20px 0;
} 

.label {
display: inline-block;
font-size: 24px;
margin: 10px;
text-align: left;
width: 200px;
} 

.input {
border-radius: 5px;
font-size: 24px;
padding: 10px;
width: 300px;
} 

#available-for-withdraw {
margin-top: 100px;
} 

.section-title {
font-size: 48px;
margin: 20px 0;
padding: 0;
text-align: center;
} 

.withdrawal-section {
margin: 40px 0;
text-align: center;
} 

.timer {
font-size: 24px;
margin: 20px 0;
} 

.timer-label {
display: block;
font-size: 18px;
margin: 10px 0;
}
</style>
</head>
<body>
<h1>BNB Galaxy V1</h1>
<p class="intro">The BNB Reward Pool with the tastiest daily return and lowest dev fee</p>
<div class="container">
<h2>Your Wallet</h2>
<form class="form">
<label class="label">Amount:</label>
<input class="input" type="text" name="amount" value="0">
<span>BNB</span>
<button class="btn">Invest</button>
</form>
<button class="btn" id="wc-connect-btn">Wallet Connect</button>
<div id="available-for-withdraw">
<h2 class="section-title">Available for Withdraw</h2>
<div class="form">
<label class="label">Amount:</label>
<input class="input" type="text" name="amount" value="0">
<span>BNB</span>
</div>
</div>
<div class="withdrawal-section">
<h2>AVAILABLE FOR WITHDRAW</h2>
<div class="withdrawal-bar">
<h3>AMOUNT TO WITHDRAW: <span>0 BNB</span></h3>
<input type="range" min="0" max="100" value="0" class="slider" id="withdrawal-slider">
</div>
<div class="buttons"> <button class="withdraw-btn">WITHDRAW</button>
<button class="reinvest-btn">REINVEST</button> </div>

<div class="countdown-section"> 
<h4>You withdrew <span class="countdown-hours">0</span> hours ago</h4> 
<p>YOU CAN MAKE A WITHDRAW EVERY 24 HOURS</p> 
</div> 
<script type="text/javascript">
  const connectWalletButton = document.getElementById("wc-connect-btn");
  const withdrawalSlider = document.getElementById("withdrawal-slider");
  const countdownHours = document.querySelector(".countdown-hours");
  const withdrawalBtn = document.querySelector(".withdraw-btn");

  // Handle wallet connect button click
  connectWalletButton.addEventListener("click", function() {
    // Implement your wallet connect code here
    console.log("Wallet connect button clicked");
  });

  // Handle withdrawal slider input
  withdrawalSlider.addEventListener("input", function() {
    const value = this.value;
    const withdrawalAmount = document.querySelector(".withdrawal-bar span");
    withdrawalAmount.textContent = `${value} BNB`;
  });

  // Handle withdrawal button click
  withdrawalBtn.addEventListener("click", function() {
    // Implement your withdrawal code here
    console.log("Withdraw button clicked");
  });

  // Start countdown timer for withdrawal section
  function startTimer(duration, display) {
    var timer = duration, hours, minutes, seconds;
    setInterval(function () {
        hours = parseInt(timer / 3600, 10);
        minutes = parseInt((timer % 3600) / 60, 10);
        seconds = parseInt(timer % 60, 10);

        hours = hours < 10 ? "0" + hours : hours;
        minutes = minutes < 10 ? "0" + minutes : minutes;
        seconds = seconds < 10 ? "0" + seconds : seconds;

        display.textContent = hours + ":" + minutes + ":" + seconds;

        if (--timer < 0) {
            timer = duration;
        }
    }, 1000);
  }

  const countdownDuration = 24 * 3600; // 24 hours in seconds
  startTimer(countdownDuration, countdownHours);
</script>
</body>
</html>
