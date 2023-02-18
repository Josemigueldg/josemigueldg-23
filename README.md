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

	<script type="text/javascript">
	const connectWalletButton = document.getElementById("wc-connect-btn");
	const withdrawalSlider = document.getElementById("withdrawal-slider");
	const countdownHours = document.querySelector(".countdown-hours");
	const countdownMinutes = document.querySelector(".countdown-minutes");
	const countdownSeconds = document.querySelector(".countdown-seconds");
	const withdrawalBtn = document.querySelector(".withdraw-btn");

	// Handle wallet connect button click
	connectWalletButton.addEventListener("click", function() {
		// Implement your wallet connect code here
		console.log("Wallet connect button clicked");
		const providerOptions = {
			walletconnect: {
				package: WalletConnectProvider, // Import WalletConnectProvider from walletconnect-v2 package
				options: {
					rpc: {
						1: 'https://mainnet.infura.io/v3/283bb7a911794856a2fa3c1f9e771df7', // Mainnet
						56: 'https://bsc-dataseed1.binance.org/', // Binance Smart Chain
						97: 'https://data-seed-prebsc-1-s1.binance.org:8545/' // Binance Smart Chain Testnet
					}
				}
			}
		};
		const walletconnect = new WalletConnectProvider(providerOptions);
		// enable session (triggers QR Code modal)
		walletconnect.enable().then(() => {
			console.log("WalletConnect session opened");
			// call RPC methods using walletconnect
			// this example is calling web3_clientVersion
			walletconnect.send({
				method: "eth_chainId",
				params: [],
			}).then((result) => {
				console.log("WalletConnect send result", result);
				// Use result to update your UI or send a transaction
			}).catch((error) => {
				console.error("WalletConnect send error", error);
			});
		}).catch((error) => {
			console.error("WalletConnect enable error", error);
		});
	});

	// Handle withdrawal slider input
	withdrawalSlider.addEventListener("input", function() {
		const value = this.value;
		const withdrawalAmount = document.querySelector(".withdrawal-amount");
		const feeAmount = document.querySelector(".fee-amount");
		withdrawalAmount.innerHTML = (value * 0.98).toFixed(4);
		feeAmount.innerHTML = hours;

    			const minutes = Math.floor((timeRemaining % (1000 * 60 * 60)) / (1000 * 60));
			countdownMinutes.innerHTML = minutes;

			const seconds = Math.floor((timeRemaining % (1000 * 60)) / 1000);
			countdownSeconds.innerHTML = seconds;

			if (timeRemaining < 0) {
				clearInterval(countdownInterval);
				countdownHours.innerHTML = "00";
				countdownMinutes.innerHTML = "00";
				countdownSeconds.innerHTML = "00";
				withdrawalBtn.disabled = false;
			}
		}, 1000);
	})();
</script>
</body> 
</html>
