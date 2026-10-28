<div align="center">

# EquityLedger

### Excel Trade Journal & Portfolio Tracker

A macro-free Excel workbook for recording equity trades, measuring performance,
analysing portfolio exposure, and fairly tracking multiple investors with
NAV-style unit accounting.

[Download the Excel workbook](./EquityLedger.xlsx?raw=1)

**Microsoft 365 or Excel 2021+ · 13 worksheets · No macros · USD**

</div>

> [!NOTE]
> The workbook contains fictional demonstration data so every dashboard is
> populated on first open. Clear the white input cells and replace the examples
> before using it as your own journal. Market prices are entered manually; the
> workbook does not connect to a broker or live-price service.

![Portfolio Analysis dashboard showing holdings, account statistics, allocation charts, themes, sub-themes and unrealised profit or loss](https://github.com/user-attachments/assets/4dfb409d-801a-49fc-b408-2c8dd2ef01fa)

*Portfolio Analysis values every open position at its latest entered price and
shows allocation, concentration, cash, exposure and unrealised performance.*

## What EquityLedger does

EquityLedger keeps the journal, portfolio and investor ledger in one `.xlsx`
file. Enter activity once in the Trade Log and the protected formula sheets
turn it into portfolio, risk and performance analysis.

| Area | What is tracked |
| --- | --- |
| Trade planning | Entry, direction, shares, stop, target, planned risk, position size and planned R multiple |
| Trade results | Exit, duration, gross and net P/L, costs, achieved R, trade gain and account change |
| Account activity | Deposits, withdrawals, dividends, fees and running account balance |
| Portfolio | Average cost, cost basis, current value, unrealised P/L, cash and position weights |
| Performance | Monthly and yearly results, compounded returns, TWR, Sharpe, Sortino and beta |
| Review | Win rate, expectancy, streaks, holding periods, discipline, mistakes and strategy comparisons |
| Investors | Units held, ownership, current value, net contribution, profit/loss and return |

## Trade journal

The Trade Log is the workbook's source ledger. It supports `Trade`,
`Scale In/Out`, `Deposit`, `Withdrawal`, `Dividend` and `Fee` entries. Trade
rows capture the market, strategy, long/short direction, entry and exit,
position size, stop loss, target, costs, screenshots, discipline score, notes,
mistakes and holding horizon.

Calculated fields include:

- planned stop-loss percentage, trade size and reward-to-risk ratio;
- gross and net profit/loss after trade costs;
- planned and achieved R multiples;
- percentage of the account risked and change in account value;
- trade duration, winning/losing classification and running account balance;
- open-position unrealised P/L using the manually entered current price.

![Trade Log with entries, trade management, exits, results and cash movements](https://github.com/user-attachments/assets/b4e3a462-79b9-456c-af7a-8e5aa04c08ad)

## Portfolio analysis

Open Trade Log positions flow into Portfolio Analysis and are consolidated by
ticker. The sheet calculates shares held, average cost, cost basis, market
value, unrealised P/L, percentage of invested capital and percentage of the
total account.

It also shows:

- invested market value, total account value, cash balance and cash percentage;
- number of holdings, largest-position weight and combined top-three weight;
- allocation by theme, sub-theme, sector and security type;
- gain/loss by holding and a rules-based diversification score.

Themes, sub-themes, sectors and types are configurable on Journal Variables.
Update **Current Price** in Trade Log column `AC` and **Prices As Of** in cell
`J5` whenever market prices are refreshed.

## Performance over time

Realised P/L is booked in the month a position closes, net of trade costs.
Open positions remain unrealised and are analysed separately. Performance Over
Time provides monthly and annual realised P/L, monthly return percentages,
compounded yearly returns, cash-flow summaries and performance by holding
horizon.

![Performance Over Time with monthly realised P/L, returns, annual summaries, holding horizons and charts](https://github.com/user-attachments/assets/dbbac24b-d531-4366-ad74-eefb59956707)

For benchmark analysis, paste monthly figures from a broker performance report:

1. your account's time-weighted return (TWR);
2. month-end account value or NAV;
3. S&P 500 monthly return; and
4. Nasdaq-100 monthly return.

The workbook then updates cumulative comparisons, total and annualised return,
benchmark gaps, rolling charts, annualised Sharpe and Sortino ratios, and beta
versus the S&P 500. If the broker does not report TWR, the workbook documents
the approximation:

```text
(Ending NAV - Starting NAV - Net Deposits) / (Starting NAV + Net Deposits)
```

## Strategy and equity analysis

Strategy Summary compares up to 14 user-defined strategies side by side.
Equities Summary applies the same framework to individual tickers. Scale-ins
and scale-outs can be treated as parts of one trade or analysed separately.

Statistics include:

- closed and open trades, winners, losers, break-even trades and win rate;
- average and largest winners and losers;
- realised, unrealised and total P/L, trade costs and expectancy;
- average risk and reward percentages;
- planned versus achieved reward-to-risk ratios;
- average holding time overall and for winners and losers; and
- average discipline rating.

![Strategy Summary comparing statistics across trading strategies](https://github.com/user-attachments/assets/de78689b-45fa-4d25-8fea-a89e2ff5094f)

## Fair multi-investor unit accounting

Investor Tracker unitises the account in a fund-like way. A deposit buys units
at the account's unit price immediately before that cash flow; a withdrawal
redeems units at the same prevailing price. This prevents a later investor from
receiving gains earned before they contributed and prevents an earlier investor
from absorbing another investor's withdrawal.

```text
Unit price at cash flow = Account value before cash flow / Units before
Units issued or redeemed = Cash amount / Unit price at cash flow

Current unit price = Account value including unrealised P/L / Total units
Investor ownership = Investor units / Total units
Investor current value = Investor units x Current unit price
Investor P/L = Current value - Net contributed
Investor return = Investor P/L / Net contributed
```

The first contribution starts at a unit price of `1.00`. Deposits issue positive
units and withdrawals redeem units. Dividends, fees, realised results and open
position P/L change the account value—and therefore the unit price—without
changing the number of investor units.

Add investor names on Journal Variables, then select the appropriate investor
on every Deposit and Withdrawal row. Cash flows without an investor remain
unassigned, so assigning each one is essential for complete ownership totals.

![Investor Tracker showing unit price, units held, ownership, investor values, profit or loss and returns](https://github.com/user-attachments/assets/c4d8b901-28ff-4665-b1d9-187476347e69)

> [!IMPORTANT]
> This is an internal record-keeping calculation, not audited fund accounting.
> Verify the unit ledger independently before using it for real capital,
> reporting, fees or distributions.

## Workbook map

| Worksheet | Purpose |
| --- | --- |
| **Start Here** | Setup checklist, operating instructions, limits and editable-cell guide |
| **Dashboard** | High-level win rate, journal statistics, account results and rolling charts |
| **Portfolio Analysis** | Open holdings, cash, allocation, concentration and diversification |
| **Performance Over Time** | Monthly/yearly returns, benchmarks, holding horizons and cumulative results |
| **Trade Log** | Primary ledger for trades, cash flows, open prices, notes and investor assignment |
| **Trade Summary** | Overall, yearly, monthly and strategy-filtered trade statistics |
| **Strategy Summary** | Side-by-side analysis of up to 14 strategies |
| **Equities Summary** | Side-by-side analysis of configured equities/tickers |
| **Investor Tracker** | NAV-style units, ownership, current value and return by investor |
| **P&L Tracker** | Daily closing P/L over a selected date range |
| **Mistakes Tracker** | Frequency and financial impact of user-defined trading mistakes |
| **Risk Calculator** | Risk-based share sizing, capital required and target/stop validation |
| **Journal Variables** | Equities, classifications, years, strategies, mistakes and investors |

## Getting started

1. Download [EquityLedger.xlsx](./EquityLedger.xlsx?raw=1) and open it in
   Microsoft 365 or Excel 2021+.
2. Read **Start Here** before clearing the fictional demo entries.
3. Set the starting account balance, journal start date and price date.
4. Configure equities, themes, sectors, strategies, mistakes and investors on
   **Journal Variables** without leaving gaps between list entries.
5. Set the maximum percentage risk per trade on **Risk Calculator**.
6. Enter new activity in the next empty **Trade Log** row. Do not insert or
   delete complete rows because formulas are prefilled through row 2000.
7. For an open trade, keep its Current Price updated. When it closes, enter the
   exit price, exit date/time and costs.
8. Review the dashboards and periodically paste monthly broker performance data
   into the benchmark table on **Performance Over Time**.

Formula cells, headers and charts are protected. The intended input cells remain
editable; unprotect a sheet only when deliberately modifying its calculations.

## Capacity and compatibility

| Item | Included capacity |
| --- | ---: |
| Trade Log | Rows 9–2000, approximately 1,992 activity entries |
| Equities | 30 configured instruments |
| Strategies | 14 strategies |
| Mistakes | 45 mistake labels |
| Investors | 45 investor names |
| P&L Tracker | Up to 1,000 trading days |
| Benchmark history | Up to 100 monthly observations |
| Default annual tables | 2024–2030; extend Journal Variables and tables for later years |
| Trade Summary monthly history | Through December 2038 |

The workbook is an `.xlsx` file and contains no VBA or macros. Some formulas
require Microsoft 365 or Excel 2021+; older Excel releases can display
`#NAME?`. Compatibility with other spreadsheet applications is not guaranteed.

## Data and risk notice

- The included trades, investors and benchmark returns are fictional examples.
- Keep backup copies before clearing data or changing protected formulas.
- Current prices and broker performance figures must be updated manually.
- Results depend on complete, correctly dated entries and accurate investor
  assignment for every deposit and withdrawal.
- Spreadsheet calculations can contain errors and should be independently
  reconciled against broker statements.

## Disclaimer

EquityLedger is provided for educational and personal record-keeping purposes.
It is not investment, accounting, tax, legal or financial advice, and it does
not guarantee the accuracy of any calculation or investment outcome. You remain
responsible for verifying all records and decisions.

Created by **Rifat Tahmid**.
