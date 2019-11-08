# Development Plan

### Active Tasks

- [JN] Add feature to scrape ALL expiration date data
- [DB] Persist ticker groups in new SQL table
- [DB] Persist ticker data (convert JN to FLASK) so we can automate the scrape/data fetching process
  Scrape all -> once per day (for now) at around 2:00 (Eastern)
- [API] Create a route that will fetch the database info for all tickers
- [VIZ] Build the call/put vol vs strike charts & call/put strike vs last price (4 total)
- [VIZ] Implement toggle on/off for any single ticker
- [VIZ] Live update to the charts (socket, etc)

### High-Level Tasks

#### 1. Data Collection and Processing (BS/JN)
- Web Scraping
  - Get as much data as possible
  - TODO: list of groups (tickers)

- Database Persistence
  - (Optional, optimization) re-configure DB from SQLite to PostgreSQL
  - [MVP+] Archiving old data

#### 2. API Development (DB/Flask)
NOTE: 
- Routes
  - Single ticker fetch
    - calls
    - puts
  - Multiple ticker fetch (groups/sectors/etc)
    - calls
    - puts

#### 3. Visualization (HTML/JS)
Control Flow (order of actions):

Expiration Date? -> Group Selection -> Single Selection (potential nested view) -> Multiple Expiration Dates (Available)

- group view
  - [viz] *both charts should be updated at once*
  - [action] toggle individual tickers on legend
  - [action] single ticker toggle
- single ticker view
  - [action] toggle individual expiration dates

#### Features (MVP+)
- single ticker price/volume history (moving average)
- calls/puts visualized together

#### Notes
- Groups -> same expiration schedule?
- 