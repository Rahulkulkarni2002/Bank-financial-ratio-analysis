# Bank Financial Ratio Analysis

A financial ratio analysis comparing three major banks, JPMorgan Chase, Goldman Sachs, and Morgan Stanley, using real data pulled directly from their SEC filings.

## What this project is about

I wanted to actually understand how to read and compare bank financials, not just calculate ratios for the sake of it. So I pulled the real income statements and balance sheets for these three banks straight from SEC EDGAR, calculated five core ratios for 2024 and 2025, and tried to explain why the numbers looked the way they did instead of just reporting them.

## The ratios

**ROE (Return on Equity)** is Net Income divided by Total Equity. This is basically how much money shareholders are getting back for what they've invested in the bank.

**ROA (Return on Assets)** is Net Income divided by Total Assets. This shows how well the bank is using everything it owns, loans, cash, securities, all of it, to generate profit.

**NIM (Net Interest Margin)** is Net Interest Income divided by Total Assets. This is the spread between what the bank earns on loans and what it pays out on deposits. Basically, how good the bank's core lending business is.

**Efficiency Ratio** is Total Expenses divided by Total Revenue. How much it costs the bank to make a dollar. Lower is better here.

**Debt to Equity** is Total Liabilities divided by Total Equity. This looks high for banks, 10x plus, compared to normal companies, but that's expected since banks run on deposits, which count as liabilities, so this isn't a red flag like it would be for a regular company.

## How these connect

I noticed these ratios aren't really separate things, they build on each other. NIM and Efficiency Ratio together basically decide how good ROA is. Then Debt to Equity takes that ROA and stretches it into ROE, because most of a bank's money isn't even its own, it's deposits. So a bank can get a strong ROE either by actually running a good business, strong NIM, low costs, or by just using more leverage to boost the number. That difference is what I tried to dig into for each bank.

## What I found

JPMorgan came out ahead on basically every core number, best NIM, lowest efficiency ratio, so it had the best ROA of the three. It also used the least leverage, meaning its ROE is coming from real performance and not just from borrowing more. Its numbers did dip slightly in 2025, mostly because it set aside a lot more money for potential loan losses that year.

Goldman Sachs improved across the board, but its efficiency ratio actually got worse at the same time, so it's costing them more to run the business. What really stood out is that Goldman runs way more leverage than the other two, and that's a big part of why its ROE looks competitive even though its actual lending business, NIM, is the weakest of the three.

Morgan Stanley was kind of in the middle everywhere, but its biggest story was cost control. Its efficiency ratio actually got better while everything else stayed pretty flat, so its ROE improvement seems to be coming from cutting costs rather than the business getting stronger or leverage going up.

Overall takeaway for me: two banks can have a similar ROE and get there in completely different ways, one through real business strength and one through leverage, and you can't tell the difference just by looking at ROE alone. You have to look at what's feeding into it.

## How I pulled the data

I used a Python library called edgartools to pull the actual 10-K filings straight from SEC EDGAR instead of typing numbers in by hand. One thing that tripped me up a lot was that every bank labels the same thing differently in their filings. JPM says Net income, Goldman says Net earnings. JPM says Total stockholders equity, Morgan Stanley says Total Morgan Stanley shareholders equity. So I had to write a function that tries a few different label options instead of assuming they'd all match.

I also looked into pulling CET1, a regulatory capital ratio banks report, but it's not in the regular financial statements, it's in a separate regulatory filing section, so I left it out rather than trying to force something that wasn't really accessible this way.

## Tools I used

Python, pandas, edgartools, matplotlib

## Files in this repo

`bank.ipynb` is the full notebook, all the data pulling, ratio calculations, charts, and my write up.

`roe_comparison.png`, `roa_comparison.png`, `nim_efficiency_leverage.png` are the charts, saved as images.

## Running it yourself

1. Clone this repo
2. Run pip install edgartools pandas matplotlib
3. Open bank.ipynb and run all the cells top to bottom. It pulls live data from SEC EDGAR so you'll need internet access.

## About me

Rahul Kulkarni
M.S. Business Analytics, UC San Diego (Rady School of Management)
