
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>BNB Galaxy V1</title>
    <link rel="stylesheet" href="styles.css">
    <!--Enlace a tu archivo CSS-->
  </head>
  <body>
    <!--Aquí van tus plantillas HTML-->
    <div id="header">
      content://0@media/external/file/69374
    </div>
    <div id="withdraw">
      <!--Plantilla para el formulario de retiro-->
    </div>
    <div id="available">
      <!--Plantilla para la sección de balance disponible-->
    </div>
    <script src="scripts.js"></script>
https://josemigueldg.github.io/josemigueldg-23/
   
   }
      h1, h2, h3 {
        font-family: "Galaxy";
        color: white;
      }
      #withdraw {
        margin-top: 20px;
      }
      #withdraw input {
        width: 200px;
        height: 30px;
        font-size: 24px;
      }
      #withdraw button {
        width: 100px;
        height: 40px;
        font-size: 20px;
        margin-right: 20px;
      }
      #available {
        margin-top: 20px;
        font-size: 24px;
        color: yellow;
      }
      #invest {
        margin-top: 20px;
      }
      #invest input {
        width: 200px;
        height: 30px;
        font-size: 24px;
      }
      #invest button {
        width: 100px;
        height: 40px;
        font-size: 20px;
        margin-right: 20px;
      }
      #connect {
        position: absolute;
        top: 10px;
        right: 10px;
        font-size: 20px;
        color: white;
      }
      #wallet {
        position: absolute;
        top: 60px;
        right: 10px;
        font-size: 20px;
        color: white;
      }
    </style>
  </head>
  <body>
    <h1>BNB Galaxy V1</h1>
    <h2>The BNB Reward Pool with the tastiest daily return and lowest dev fee</h2>
    <h3>YOUR WALLET 0 ROI UP 1% TO 3% DAILY REFERRER COMMISSION 14% DEPOSIT FEE 2% WITHDRAWAL FEE 2% MARKETING 1%</h3>
    <button id="connectBtn">Connect Wallet</button>
    <div id="withdraw">
      <input type="number" placeholder="Enter amount in BNB" />
      <button id="withdrawBtn">Withdraw</button>
      <button id="reinvestBtn">Reinvest</button>
    </div>
    <div id="available">AVAILABLE FOR WITHDRAW: 0 BNB</div>
    <div id="invest">
      <input type="number" placeholder="Enter amount in BNB" />
      <button id="investBtn">Invest</button>
    </div>
    <div id="connect"></div>
    <div id="wallet"></div>
    <script>
      // Add WalletConnect functionality
      const connectBtn = document.getElementById("connectBtn");
      connectBtn.addEventListener("click", async () => {
        if (window.ethereum) {
          try {
            await window.ethereum.enable();
            const accounts = await window.ethereum.request({ method: 'eth_accounts' });
            const address = accounts[0];
            document.getElementById("connect").innerHTML = "Connected to wallet";
            document.getElementById("wallet").innerHTML = `Wallet: ${address}`;
            console.log("Connected to wallet: " + address);
          } catch (error) {
            console.log(error);
          }
        } else {
          console.log("Install MetaMask!");
        }
      });

      // Add functionality to withdraw and reinvest buttons
const withdrawBtn = document.getElementById("withdrawBtn");
withdrawBtn.addEventListener("click", () => {
  // Implement code to withdraw from the reward pool and send to user's wallet
  console.log("Withdraw button clicked!");
});

const reinvestBtn = document.getElementById("reinvestBtn");
reinvestBtn.addEventListener("click", () => {
  // Implement code to reinvest the user's rewards into the reward pool
  console.log("Reinvest button clicked!");

  // Get user input for amount to reinvest
  const reinvestAmount = document.querySelector("#withdraw input").value;

  // Check that user input is valid
  if (isNaN(reinvestAmount) || reinvestAmount <= 0) {
    console.log("Invalid reinvestment amount.");
    return;
  }

  // Call smart contract function to reinvest user's rewards
  // For example: myContract.reinvest(reinvestAmount);

  // Update available balance after reinvestment
  const availableBalance = document.getElementById("available");
  availableBalance.textContent = `AVAILABLE FOR WITHDRAW: ${0} BNB`;
});

// Add functionality to invest button
const investBtn = document.getElementById("investBtn");
investBtn.addEventListener("click", () => {
  // Get user input for amount to invest
  const investAmount = document.querySelector("#invest input").value;

  // Check that user input is valid
  if (isNaN(investAmount) || investAmount <= 0) {
    console.log("Invalid investment amount.");
    return;
  }

  // Call smart contract function to invest user's funds
  // For example: myContract.invest(investAmount);

  // Update available balance after investment
  const availableBalance = document.getElementById("available");
  availableBalance.textContent = `AVAILABLE FOR WITHDRAW: ${0} BNB`;
});
