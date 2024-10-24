# Amplify Integration - Stock API

A stock quote and watch list API based on [**Yahoo Finance**](https://financeapi.net/) created in Amplify Integration.

Check out a more updated stock quote/watchllist API created in Amplify Integration [here](https://github.com/lbrenman/ai-stockquote-fh)

The project exposes two end points
* `GET /quote?symbol=AAPL`
* `GET /watchlist?symbols=AAPL,INTC,TXN,NVDA,AMZN,MSFT`

The `quote` API is basically a pass through of the Yahoo quote API with a reduced and field mapped payload. It takes a single symbol as a query parameter. The `watchlist` API returns an array of highly reduced stock quotes suitable for a watch list. It takes a comma separated list of symbols.

The project is intended to be a simple example of how to expose API endpoints and map and aggregate data in Amplify Integration.

An OpenAPI 3.0 doc is provided as well.

## Quote

`GET /quote?symbol=AAPL`

```json
{
  "ChangePercent": -1.2462649,
  "Price": 211.57,
  "Change": -2.6699982,
  "DayHigh": 215.17,
  "DayLow": 211.3,
  "Volume": 55039753,
  "Name": "Apple Inc.",
  "Symbol": "AAPL",
  "FiftyTwoWeekLow": 164.08,
  "FiftyTwoWeekHigh": 220.2,
  "MarketCap": 3244235685888,
  "DividendYield": 0.47
}
```

## Watchlist

* `GET /watchlist?symbols=AAPL,INTC,TXN,NVDA,AMZN,MSFT`

```json
[
  {
    "ChangePercent": -0.8168409,
    "Price": 212.49,
    "Change": -1.75,
    "Volume": 65802837,
    "Symbol": "AAPL",
    "Name": "Apple"
  },
  {
    "ChangePercent": -0.03282443,
    "Price": 30.45,
    "Change": -0.0099983215,
    "Volume": 26217798,
    "Symbol": "INTC",
    "Name": "Intel"
  },
  {
    "ChangePercent": -1.212556,
    "Price": 193.9,
    "Change": -2.380005,
    "Volume": 3286353,
    "Symbol": "TXN",
    "Name": "Intel"
  },
  {
    "ChangePercent": 1.7514113,
    "Price": 131.88,
    "Change": 2.2700043,
    "Volume": 297485100,
    "Symbol": "NVDA",
    "Name": "NVIDIA"
  },
  {
    "ChangePercent": -0.09247575,
    "Price": 183.66,
    "Change": -0.16999817,
    "Volume": 21388177,
    "Symbol": "AMZN",
    "Name": "Amazon.com"
  },
  {
    "ChangePercent": 0.22419964,
    "Price": 442.57,
    "Change": 0.99002075,
    "Volume": 12104244,
    "Symbol": "MSFT",
    "Name": "Microsoft"
  }
]
```

## Installation

* Import the `StockQuote.zip` project into Amplify Integration
* Edit the Yahoo Finance connector and enter your API Key
  * You can get an API Key [**here**](https://financeapi.net/)
* Enable your integrations
* Call your API