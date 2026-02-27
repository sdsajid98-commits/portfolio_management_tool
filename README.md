markdown
# Multi‑Asset Portfolio Manager

A Python project that models a portfolio containing different types of assets – stocks, bonds, and real estate. It demonstrates object‑oriented programming with inheritance, abstract base classes, operator overloading, and practical financial calculations.

## What the code does

- Defines an abstract `Asset` class with common attributes (`name`, `quantity`, `purchase_price`, `current_price`) and an abstract method `current_value`.
- Creates concrete subclasses:
  - `Stock` (adds `symbol` and `shares` properties, `cost_basis`)
  - `Bond` (adds `coupon_rate`, `maturity_date`)
  - `RealEstate` (adds `location`, `square_feet`)
- All subclasses inherit `profit_loss`, `__repr__`, and `__str__` from `Asset`.
- A `Portfolio` class holds a list of assets and provides methods to:
  - Add/remove assets
  - Calculate total value, cost basis, and profit/loss (with a timing decorator)
  - Merge two portfolios using `+` (returns new portfolio) and `+=` (in‑place)
  - Load stocks from a CSV file (using pandas)
  - Filter assets by current value (using `filter` and `map`)
  - Display holdings with `enumerate`
- Logging and custom exceptions (`InvalidQuantityError`, `InvalidPriceError`) for input validation.
- A short demonstration at the bottom of the file (runs when you execute the script directly).

## Requirements

- Python 3.7 or newer
- pandas (only needed for the CSV loading feature)

Install pandas with:
```bash
pip install pandas
```
How to run
Save the Python file (e.g., portfolio_tool.py).

Run it:

bash
python portfolio_tool.py
This will execute the built‑in demo, creating some assets and a portfolio, then printing a few results.

Using the classes in your own code
You can import the classes and build your own portfolios:

python
from portfolio_tool import Stock, Bond, RealEstate, Portfolio

# Create assets
aapl = Stock("AAPL", 10, 150.0, 175.0)
bond = Bond("US10Y", 1000, 95.0, 98.0, 0.02, "2030-12-31")
warehouse = RealEstate("Warehouse", 1, 500000, 550000, "Chicago", 10000)

# Create a portfolio and add assets
my_portfolio = Portfolio("My Mix")
my_portfolio.add_stock(aapl)
my_portfolio.add_stock(bond)
my_portfolio.add_stock(warehouse)

# Get totals
print(f"Total value: ${my_portfolio.total_value():,.2f}")
print(f"Total profit/loss: ${my_portfolio.total_profit_loss():,.2f}")
File structure
Custom exception classes

Asset (abstract base class)

Stock, Bond, RealEstate (subclasses)

time_decorator (for timing methods)

Portfolio class (with all methods)

A small demo (if __name__ == "__main__" block)

Example output from the built‑in demo
text
INFO:root:Asset object created. Quantity: 10, Name: AAPL
INFO:root:Asset object created. Quantity: 1000, Name: US10Y
INFO:root:Asset object created. Quantity: 1, Name: Warehouse
INFO:root:My Portfolio Portfolio object created.
Holdings: ['AAPL', 'US10Y', 'Warehouse']
Total value: 873000.0
Total cost: 786000.0
Profit/loss: 87000.0
Merged size: 4
What I learned / why this project
I built this to practice:

Inheritance and abstract base classes (ABC, @abstractmethod)

Operator overloading (__add__, __iadd__)

Using super() to initialise parent classes

Properties, class methods, static methods

Functional programming tools (filter, map)

Logging and custom exceptions

File I/O (CSV loading)

It’s also a practical foundation for a financial analysis tool – something I can extend later with live data or visualisations.

Notes / quirks
The CSV loader expects columns exactly named symbol, shares, purchase_price, current_price. Extra columns are ignored.

The time_decorator logs execution time – you’ll see those messages if logging level is INFO.

When you merge portfolios with +, the new portfolio gets the name "MergedPortfolio" (you can rename it afterwards).

The add_stock method currently accepts any asset (stocks, bonds, real estate) – the name is a bit misleading but works.

License
Free to use, modify, and learn from.

text


Copy everything above (from `# Multi‑Asset Portfolio Manager` to the end) and paste it into your `README.md` file. Save it, commit, and push to GitHub – it will look great.
