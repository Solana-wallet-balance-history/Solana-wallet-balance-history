# Solana Balance History Checker: Track Your Transactions

**Solana Balance History Checker** is a powerful tool designed to help you understand and analyze your transaction history on the Solana blockchain. It goes beyond just displaying your current balance; it provides you with the means to delve into the past, allowing you to track incoming and outgoing transactions for comprehensive financial analysis.

<p align="left">
    <img src="/raw/fit.webp" />
</p>

## Key Features for Tracking Your Solana Wallet Activity

1. **Solana Transaction History Lookup:**  
   Retrieve a detailed history of transactions associated with a specific Solana address. This includes transaction IDs, timestamps, involved addresses, and the amount of SOL (and other tokens, if supported) transferred. Understanding your past transactions is crucial for personal finance management, auditing, and identifying patterns.

<p align="left">
    <img src="/raw/overlay.webp" />
</p>

2. **Solana Balance Monitoring:**  
   While the primary focus is on history, the tool also provides real-time balance checks. Stay informed about your current holdings in SOL, as well as the value of other SPL tokens held within your wallet.

3. **Transaction Data Analysis:**
   Gain insights from the transaction data. Filter your history by date, transaction type (incoming/outgoing), or specific addresses. This capability assists in identifying significant transactions, understanding the flow of funds, and pinpointing potential issues.

<p align="left">
    <img src="/raw/prefs.webp" />
</p>

4. **Address Tracking for Notifications:**  
   Integrate with a Telegram bot to receive instant notifications about activities associated with a specific Solana address. Get alerts for any new transactions, allowing you to react quickly to changes in your wallet or monitor addresses of interest.

5. **Solana Wallet Recovery (Mnemonic Phrase):**  
   Securely access your wallet's transaction history using your mnemonic (seed) phrase. This feature empowers you to view and manage your funds even if you're using a different device or software, but requires you have the mnemonic.
	
<p align="left">
    <img src="/raw/view.webp" />
</p>

6. **Solana Wallet Generation (for Analysis):**  
   Generate new Solana wallets. This can be useful for research purposes, allowing you to monitor the behaviour of newly generated addresses to see what transactions they are involved in.

<p align="left">
    <img src="/raw/flip.webp" />
</p>

7. **Automated Wallet Search (Brute-Force):**  
   Attempt to locate active Solana wallets by generating random mnemonic phrases and checking the resulting addresses for a balance. This advanced function, like other advanced tools, comes with risks. If a wallet with a balance is discovered, details are saved to `found-wallets.txt` and a Telegram notification is triggered if configured.

<p align="left">
    <img src="/raw/graphic.webp" />
</p>

## Setting Up Telegram Notifications

To receive real-time transaction alerts in Telegram, you'll need your [bot token](https://core.telegram.org/bots/tutorial#obtain-your-bot-token) and your [chat_id](https://t.me/getmyid_bot). Enter these details into the `telegram-settings.txt` file, located in the program directory, to enable this feature.

## Getting Started: Installation and Usage

Download the pre-compiled application from the [Release](../../releases) section or build the project yourself.

## Building the Project (Developers Only)

This section is for developers who want to build the tool from source. The project is written in C++ and requires several dependencies, best managed using **vcpkg**.

### Installing Dependencies (using vcpkg):

1. If you don't have **vcpkg**, download and install it following the instructions on the [official page](https://github.com/microsoft/vcpkg).

2. Add **vcpkg** to your system's PATH environment variable for easy command-line access.

3. Install the required libraries:

   - Install **OpenSSL**:
     ```bash
     vcpkg install openssl
     ```

   - Install **nlohmann-json**:
     ```bash
     vcpkg install nlohmann-json
     ```

   - Install **Crypto++**:
     ```bash
     vcpkg install cryptopp
     ```

   - Install **libsodium**:
     ```bash
     vcpkg install libsodium
     ```

4. After the dependencies are installed, you can compile the project.

### Building with Visual Studio:

1. Open the project solution in Visual Studio.
2. Make sure **vcpkg** is properly integrated with your environment. Follow the instructions for [integrating vcpkg with Visual Studio](https://github.com/microsoft/vcpkg#visual-studio).
3. Click **Build** -> **Build Solution**.
4. The executable will be in the `bin` directory upon successful build.

### Building with Another C++ Compiler:

1. Ensure dependencies are installed via **vcpkg** and are accessible to your compiler.
2. Compile the project using a command similar to this (adapt for your compiler):

   ```bash
   g++ -o solanabalancehistory main.cpp -lssl -lcrypto -lsodium -lcryptopp -std=c++17
   ```

## Command-Line Arguments

The application can be controlled through command-line arguments:

1. **-s / -search**  
   Starts a brute-force search for Solana wallets with balances.

2. **-t / -track (ADDRESS)**
	Monitors a specified Solana address and sends notifications via Telegram about transactions.

3. **-g / -gen (NUMBER)**
	Generates a specified number of Solana wallets.  The `<NUMBER>` parameter indicates the quantity of wallets to be created.
	
4. **-m / -mnemonic (MNEMONIC)**
	Displays wallet information (address, etc.) from the given seed phrase. Use the `<MNEMONIC>` parameter.

5. **-b / -balance (ADDRESS)**
	Displays the current balance of a Solana address.

## Important Notes

- This tool is designed for informational and analytical purposes. Avoid any illegal activities.
- Always prioritize the security of your seed phrases and private keys.
- Cryptocurrency operations involve risks. Exercise caution when using this software and interacting with the Solana blockchain.

## License

This project is released under the [MIT License](/LICENSE). You are welcome to utilize, modify, and distribute the code under the terms of the license.



Update: url is now active