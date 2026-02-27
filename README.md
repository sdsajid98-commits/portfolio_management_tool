# Financial Portfolio Management System (Python)

## Overview

This project is a simple object-oriented financial portfolio management
system built in Python. I developed it as part of strengthening my
programming foundations while transitioning toward financial analyst
roles.

The goal was to simulate how different asset classes (stocks, bonds,
real estate) can be structured, validated, and analyzed within a
portfolio using clean OOP principles.

The project demonstrates:

-   Object-Oriented Programming (OOP)
-   Abstraction & Inheritance
-   Custom Exceptions
-   Properties & Class Methods
-   Operator Overloading
-   File Handling with pandas
-   Logging & Performance Timing
-   Functional programming concepts (map, filter, lambda)

------------------------------------------------------------------------

## Key Features

### 1. Asset Abstraction

An abstract base class `Asset` defines the common structure:

-   Quantity validation
-   Price validation (static method)
-   Cost basis calculation
-   Profit/Loss calculation
-   Abstract `current_value` property

All asset types inherit from this base class.

------------------------------------------------------------------------

### 2. Supported Asset Types

#### Stock

-   Symbol
-   Shares
-   Purchase price
-   Current price
-   Class method to instantiate from dictionary (useful for CSV loading)

#### Bond

-   Coupon rate
-   Maturity date
-   Market valuation

#### Real Estate

-   Location
-   Square footage
-   Current market value

------------------------------------------------------------------------

### 3. Portfolio Management

The `Portfolio` class supports:

-   Adding assets
-   Removing assets by symbol
-   Calculating total portfolio value
-   Calculating total cost basis
-   Calculating total profit/loss
-   Filtering holdings above a minimum value
-   Loading stock data from CSV
-   Merging portfolios using `+` operator
-   In-place merging using `+=`
-   Indexing support
-   Length support
-   Holdings summary generation

------------------------------------------------------------------------

### 4. Error Handling

Custom exceptions improve robustness:

-   `InvalidQuantityError`
-   `InvalidPriceError`

These ensure that invalid financial inputs are caught early.

------------------------------------------------------------------------

### 5. Performance Logging

A decorator `time_decorator` measures execution time of portfolio
valuation methods and logs results using Python's built-in `logging`
module.

------------------------------------------------------------------------

## Example Usage

``` python
aapl = Stock("AAPL", 10, 150, 175)
msft = Stock("MSFT", 5, 200, 210)

p = Portfolio("My Portfolio")
p.add_stock(aapl)
p.add_stock(msft)

print("Total value:", p.total_value())
print("Profit/loss:", p.total_profit_loss())
```

------------------------------------------------------------------------

## CSV Loading Format

The CSV file should follow this structure:

``` csv
symbol,shares,purchase_price,current_price
AAPL,10,150,175
MSFT,5,200,210
```

Load using:

``` python
p.load_from_csv("stocks.csv")
```

------------------------------------------------------------------------

## Why I Built This

Coming from a finance background, I wanted to move beyond theoretical
knowledge and build practical systems that reflect:

-   Portfolio valuation logic
-   Profit/Loss tracking
-   Asset structuring
-   Data handling workflows

Rather than using pre-built financial libraries, I implemented core
functionality from scratch to strengthen my understanding of both
programming fundamentals and financial calculations.

------------------------------------------------------------------------

## Skills Demonstrated (Relevant to Financial Analyst Roles)

-   Financial metric calculation (Cost Basis, Market Value, P/L)
-   Structured portfolio modeling
-   Data ingestion via CSV
-   Code modularity and scalability
-   Clean error handling
-   Analytical thinking translated into code
-   Basic performance profiling

------------------------------------------------------------------------

## Potential Extensions

Future improvements could include:

-   Risk metrics (volatility, beta, Sharpe ratio)
-   Portfolio allocation percentages
-   Visualization using matplotlib
-   Integration with financial APIs
-   Discounted Cash Flow (DCF) modeling
-   Bond yield-to-maturity calculation
-   Exporting portfolio reports

------------------------------------------------------------------------

## Tech Stack

-   Python 3
-   pandas
-   logging
-   time
-   abc (Abstract Base Classes)

------------------------------------------------------------------------

## Author

Built as part of my learning journey toward financial analysis and
quantitative roles. This project reflects hands-on application of
finance concepts using Python.
