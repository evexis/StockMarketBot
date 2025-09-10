**StockMarketBot**

StockMarketBot is a Python automation script that generates forecasts and market insights for currencies, cryptocurrencies, and stock indices. It automatically sends daily reports via email, with clean formatting and curated market news.

**Features**

Forecasts for:

  USD/PHP, GBP/PHP, AUD/PHP, JPY/PHP, SGD/PHP

  Bitcoin (BTC), Ethereum (ETH)

  Philippine Stock Exchange Index (PSEi)

  S&P 500

  Philippine REITs

Market news filtering (only business, finance, tech, and disruptive events)

Email reports with formatted summaries

Identifies top gainers/losers in US markets

Automated daily execution via cron job

**Requirements**

  Python 3.8+

  Virtual environment (recommended)

**Required Python libraries:**

  pip install yfinance pandas numpy plotly statsmodels beautifulsoup4 requests


Gmail App Password (for sending reports via Gmail SMTP)

**Setup**
Clone Repository
git clone https://github.com/Evexis/StockMarketBot.git
cd StockMarketBot

Create Virtual Environment
python3 -m venv venv
source venv/bin/activate

Install Requirements
pip install -r requirements.txt

Configure Email

Edit StockMarketBot.py and replace:

EMAIL_ADDRESS = "your_email@gmail.com"
EMAIL_PASSWORD = "your_app_password"
BCC_EMAIL = "bcc_email@gmail.com"


Important: Use a Google App Password instead of your regular password.

**Automation (Optional)**

To run daily at 8:00 AM (Asia/Manila), add this cron job:

crontab -e


Insert:

CRON_TZ=Asia/Manila
0 8 * * * /home/user/Documents/run_stockbot.sh

Where run_stockbot.sh contains:

#!/usr/bin/env bash
set -euo pipefail
cd /home/ecdayrit/Documents
source venv/bin/activate
/usr/bin/python3 /home/user/Documents/StockMarketBot.py >> /home/user/Documents/stockbot.log 2>&1

**Example Output**

Forecasts for Forex, Crypto, and Stocks

Top movers and market shifts

Curated business/market/tech news

Email report with formatted sections

**Contributing**

PRs and suggestions welcome! Please fork the repo and open an issue or pull request.

