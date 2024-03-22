# Alpaca News Websocket and Trading Bot README

## Overview

This project involves a Node.js application that integrates with the Alpaca Trade API and a news websocket to make trading decisions based on live news data. The bot connects to Alpaca's news stream, evaluates the impact of received news headlines, and decides whether to buy or sell a specific stock based on this impact.

## Features

- Connects to the Alpaca news websocket.
- Authenticates with the Alpaca API using environment variables.
- Subscribes to all incoming news feeds.
- Processes each news message and evaluates its impact using a GPT-3.5 model.
- Makes trading decisions (buy/sell) based on the impact score of the news headline.

## Prerequisites

Before running the bot, make sure you have:

- Node.js installed.
- An Alpaca account and your API keys (API key ID and API secret key).
- Access to OpenAI API for using GPT-3.5 model.

## Installation

1. Clone the repository or download the source code.
2. Install the required dependencies by running `npm install` in your project directory.
3. Ensure you have set up your environment variables (APCA_API_KEY_ID, APCA_API_SECRET_KEY, and OPENAI_API_KEY).

## Usage

1. Start the script using `node <filename>.js` in your terminal.
2. The script will automatically connect to the Alpaca news websocket and authenticate using your Alpaca API credentials.
3. Once connected, it subscribes to all news feeds and begins listening for incoming news messages.
4. Upon receiving a news message, the script sends the headline to OpenAI's GPT-3.5 model to evaluate its impact.
5. Based on the impact score returned by the model, the script decides whether to buy or sell the stock associated with the news article.
   - If the impact score is equal to or higher than 75, it buys the stock.
   - If the impact score is equal to or lower than 65, it sells the stock.

## Environment Variables

Ensure these environment variables are set before running the script:

- `APCA_API_KEY_ID`: Your Alpaca API key ID.
- `APCA_API_SECRET_KEY`: Your Alpaca API secret key.
- `OPENAI_API_KEY`: Your OpenAI API key for GPT-3.5 model requests.

## Important Notes

- The trading strategy implemented in this script is rudimentary and serves only as an example. Real-world trading involves risks, and it is recommended to backtest any strategy before live deployment.
- The use of the OpenAI model to evaluate news impact is an example of integrating AI into trading decisions. Ensure compliance with OpenAI's use case policies and guidelines.

## Disclaimer

This software is provided as-is, with no guarantees of any kind. The creator is not responsible for any financial losses incurred through the use of this software. Always review and understand any code you run connected to financial trading.
