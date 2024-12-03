# Raydium Volume Bot

Welcome to the Raydium Volume Bot! This innovative tool is designed to automate trading activities on the Raydium platform, increasing volume and liquidity by distributing SOL to multiple wallets for continuous buying and selling. It offers a range of powerful features to optimize trading efficiency and market impact.

## Key Features

- **Automated Wallet Creation**: Effortlessly generate multiple wallets for decentralized trading and volume expansion.
- **Automated SOL Distribution**: Seamlessly distribute SOL to each new wallet, ensuring balanced trading across accounts.
- **Endless Buy and Sell Cycles**: The bot continuously buys and sells assets, creating perpetual trading volume without manual intervention.
- **Advanced Swapping with Jupiter V6**: Leverages the Jupiter V6 swap aggregator to execute efficient and optimized token swaps.
- **Configurable Parameters**: Tailor buy amounts, trade intervals, distribution settings, and more to suit your specific trading strategy.

## Getting Started

### 📋 Environment Variables

The bot uses the following environment variables. Rename the `.env.copy` file to `.env` and set the necessary variables.

```env
PRIVATE_KEY=                 # Private key for the main wallet
RPC_ENDPOINT=                # RPC endpoint for Solana
RPC_WEBSOCKET_ENDPOINT=      # RPC WebSocket endpoint for Solana

####### BUY SETTING #######
BUY_UPPER_PERCENT=60         # Higher percent limit of SOL that can be used to buy token in wallet
BUY_LOWER_PERCENT=30         # Lower percent limit of SOL (30 means, it buys with larger than 30% of SOL in wallet when buy)

BUY_INTERVAL_MAX=30          # Upper limit of seconds to wait after second buy
BUY_INTERVAL_MIN=2           # Lower limit of seconds (it waits from 2 to 30 secs after second buy before second buy)

SELL_INTERVAL_MAX=30         # Upper limit of seconds to wait after sell
SELL_INTERVAL_MIN=3          # Lower limit of seconds (it waits from 2 to 30 secs after sell to transfer SOL)

DISTRIBUTE_WALLET_NUM=4      # Number of wallets that run in parallel which makes volume (max: 20)

SLIPPAGE=50                  # Slippage in percent

TOKEN_MINT=                  # Mint address of token to increase volume
```


1. Clone the repository
To begin, clone the repository to your local machine.
```
git clone https://github.com/knightworlds/Raydium-Volume-Bot.git
cd Raydium-Volume-Bot
```

2. Install dependencies
Install the required dependencies using npm:
```
npm install
```

3. Configure the environment variables

Rename the .env.example file to .env and set the necessary environment variables, including:
- RPC and WSS configurations
- The secret key for the main wallet
- Jito authentication keypair

4. Run the bot
Once everything is set up, you can start the bot with the following command:
```
npm run start
```

## Key Differences Between the Previous and Updated Versions


### 🚫 Limitations of the Previous Version

- ❌ **Repetitive Buy & Sell on a Single Wallet**: The old version relied on fixed wallets for buy/sell actions, which made it easy to spot repetitive transactions on DexScreener.
- ❌ **No Increase in Makers**: It only increased trading volume without adding new makers to the pool, limiting the overall liquidity impact.
- ❌ **Token Gathering without Selling**: In the past, leftover tokens were simply gathered to the main wallet without selling them, leaving unnecessary token balances.
- ❌ **Equal Number of Buys and Sells**: The strategy of matching buys and sells created sell pressure after each round of trading, potentially impacting the market negatively.


### 🚀 Improvements in the Updated Version

- ✅ **Automated SOL Transfers to New Wallets**: After completing a buy and sell cycle on one wallet, the bot automatically transfers SOL to a new wallet and continues trading there. This increases the number of unique wallets involved in the trading process, making the volume appear more organic.
- ✅ **Increased Pool Makers**: The new version creates a fresh wallet after each round of buying and selling, contributing to a more substantial number of market makers and increasing liquidity.
- ✅ **Selling Tokens Before Gathering SOL**: The bot now ensures that any remaining tokens are sold before gathering, preventing unused tokens from accumulating in the wallet. This strategy also reclaims token account rent fees (0.00203 SOL).
- ✅ **More Buys than Sells**: The updated bot executes two buys for every sell, creating buy pressure by increasing the number of buy transactions compared to sells. This results in more favorable market conditions.


## Why Work with Me?

As the creator of the Raydium Volume Bot and other advanced trading tools, I am dedicated to providing high-quality, customizable solutions to meet your specific trading needs. Whether you're looking to enhance liquidity, execute complex strategies, or automate your trading processes, I can provide the expertise and tools to help you succeed.


## 👤 Contact Me

#### Discord: [@knightworlds](https://discordapp.com/users/965772784653443215)

#### Twitter: [@knightworlds127](https://twitter.com/knightworlds127)   

#### Telegram: [@knightworlds](https://t.me/knightworlds)   


### I am also available to assist with a variety of other bots, including:
- Raydium Sniping Bot
- Token-Freezer
- Super Raydium Volume bot V3 (Target any interval, any amount, any volume and any number of makers with enough Balance of the wallet)
- Perpetual Market Maker bot
- Multi-DEX Volume Booster
- Raydium sniper using Yellow-Stone GRPC within 1st second
- Pumpfun sniper & bundler
- Raydium bundler with more than 20 wallets
- Raydium Volume booster
- Shit-token Launcher using raydium bundler
- Holder booster
- Copytrading bot
- Arbitrage bot 

Let’s work together to boost your trading strategies!
