# DPU K-Food Customer Report

An analysis of order records from DPU K-Food, a Korean meal pre-order and pickup business I started and ran at DePauw University in Greencastle, Indiana, in fall 2024. It tests whether Korean food sells to college students in the US who are not Korean.

**[View the report →](https://hyeseongo.github.io/dpu-kfood-report/)**

## The question

I kept hearing that Korean food was catching on in the US and wanted to see whether that held outside the Korean community. The test was whether people who are not Korean would buy Korean food and then come back, measured with real sales instead of a survey.

## Key findings

- Over 10 weeks and 8 pickups, 72 people placed 156 orders. Counting one catering order and one group order, the business served 348 meals and took in about $2.5K.
- Of the 59 customers whose origin is known, 47 (80%) were not Korean. Half of all customers (36 of 72) ordered again. Non-Korean customers reordered at 51% and Korean customers at 67%, a gap that is not statistically meaningful (Fisher's exact test, p = 0.52).
- Growth stalled when new customers stopped arriving, while regulars kept ordering. The first two pickups brought 33 and 21 new customers. The remaining six brought 18 combined.
- One fraternity catering order ($333) earned about twice the average late-season pickup ($167 across pickups 4–8).

## What I did

The order records were eight spreadsheets, one per pickup, each laid out differently. I merged them into one table with Python (pandas) and checked that every rebuilt pickup total matched the sheet's own total.

Customers were recorded by name only, and the same person was often spelled differently each week. I grouped those variants (the team confirmed the uncertain ones), replaced every customer with an anonymous ID, and dropped phone numbers.

To compare groups, I labeled each customer's nationality from memory using an alphabetical name list with order history hidden, to reduce bias from knowing who ordered often. Anyone I was unsure about stayed Unknown (13 of 72).

With the clean table I measured repeat rates by first-order cohort, compared Korean and non-Korean repeat rates with Fisher's exact test and checked the 141 pre-launch survey responses against what people actually bought.

## What I'd do next

The next version would sell to Greek houses. DePauw has 15 fraternities and sororities living in their own chapter houses and none of them serve meals on weekends, so members already pay for weekend food. The plan is a monthly standing catering order with a minimum headcount, priced lower in exchange for that commitment (gross margin down from about 50% to 40%). Individual orders would pause or stay small on catering days.

## Tools

Python with pandas, openpyxl and scipy handled cleaning, reading the Excel file and the statistics. The report is a single HTML page with hand-built SVG charts and no chart library. It has light and dark themes and a mobile layout, and it is hosted on GitHub Pages.

## Data and privacy

The raw order sheets and the analysis scripts contain customer names and phone numbers, so neither is published. This repository holds only the report, which shows aggregate figures.

## Author

Hyeseong Oh, DePauw University, B.A. in Business Analytics and Computer Science (expected December 2027)

LinkedIn: [Hyeseong Oh](https://www.linkedin.com/in/hyeseong-oh-722a712ba/)
