#josemigueldg23

<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>BNB Galaxy V1</title>
    <style>
      body {
        background-color: purple;
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
    <script>
      // Add WalletConnect functionality
      const connectBtn = document.getElementById("connectBtn");
      connectBtn.addEventListener("click", async () => {
        if (window.ethereum) {
          try {
            await window.ethereum.enable();
            console.log("Connected to wallet!");
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
      });
    </script>
  </body>
</html>
