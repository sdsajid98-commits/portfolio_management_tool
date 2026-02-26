# Portfolio Management Tool

A Python project that models stock holdings and portfolios. It helps track investments, calculate gains/losses, and analyse sector exposure. Built as a learning exercise and portfolio piece for a Financial Analyst role.

## What it does

- Create individual `Stock` objects with validation (no negative shares or prices).
- Build a `Portfolio` that holds multiple stocks.
- Load holdings from a CSV file (columns: symbol, shares, purchase_price, current_price).
- Display holdings in a clean numbered list.
- Filter stocks by current value (using `filter` and `map`).
- Compute total portfolio value, cost basis, and profit/loss – with a timing decorator to log execution time.
- Use logging to record key events (creation, additions, removals).

## Why I built it

I wanted to combine my interest in finance with Python skills. This project covers OOP, exception handling, decorators, functional programming (`filter`, `map`), and file I/O – all topics I’ve been learning. It’s the foundation for a larger analytics tool I plan to expand.

## Getting Started

### Prerequisites

- Python 3.7+
- pandas (`pip install pandas`)

### Installation

1. Clone the repo (or just download the `.py` file).
2. Install pandas if you don’t have it:
   ```bash
   pip install pandas

Usage
Run the script directly – it includes a demo that:

Creates a sample CSV (sample_portfolio.csv).

Loads it into a portfolio.

Prints holdings, filters stocks, and shows totals.

bash
python portfolio_tool.py
You can also import the classes and use them in your own scripts:

python
from portfolio_tool import Stock, Portfolio

my_stock = Stock("AAPL", 10, 150.0, 175.0)
my_portfolio = Portfolio("My Fund")
my_portfolio.add_stock(my_stock)
print(my_portfolio.total_value())
Example Output
text
Created sample CSV: sample_portfolio.csv
INFO:root:Portfolio 'Retirement Fund' created
INFO:root:Stock created: AAPL (10 shares)
...
1. AAPL
2. MSFT
3. TSLA
4. JPM

Stocks with current value > $1000: ['AAPL', 'MSFT', 'TSLA']

Total portfolio value: $5,230.00
Total cost basis: $4,750.00
Total profit/loss: $480.00
Known Quirks
The CSV must have the exact column names: symbol, shares, purchase_price, current_price. (Extra columns are ignored.)