# Coinduck
Data Methodology and Sources
Transparency is core to how CoinDuck https://www.coinduck.io/ operates. This page explains where our data comes from, how it is calculated, how often it updates, and what happens when data is unavailable.

Data Sources
CoinDuck aggregates data from multiple sources to ensure accuracy and coverage. Exchange market data (prices, volume, funding rates, open interest) is collected via public APIs and websocket feeds directly from each protocol. On-chain data (TVL, fees, revenue) is sourced from blockchain indexers and smart contract event logs. All data is normalized to USD using current market rates for consistent cross-protocol comparisons.

Update Frequency
Different metrics update at different intervals depending on the data source. Market prices and trading activity update in near real-time via websocket connections. Aggregate dashboards such as volume, open interest, and funding rates revalidate every 1 to 5 minutes. TVL data revalidates every 5 to 15 minutes. Fee and revenue data is aggregated daily and revalidated on a short interval. The specific revalidation interval for each dashboard is shown in the page metadata.

Metric Definitions
Trading Volume
The total notional value of trades executed on a protocol within a given time period (24h, 7d, or 30d). Measured in USD. Only executed trades are counted — pending orders and cancelations are excluded.

Open Interest
The total notional value of all outstanding derivative contracts (perpetual futures, options) that have not been settled. Measured in USD as a snapshot at the time of data collection.

Total Value Locked (TVL)
The total value of crypto assets deposited into a protocol's smart contracts. Includes tokens in lending pools, liquidity pools, staking contracts, and other on-chain deposits. Only non-custodial, on-chain deposits are counted.

Funding Rate
The periodic payment exchanged between long and short traders in perpetual futures markets. Expressed as a percentage. Positive rates mean longs pay shorts; negative rates mean shorts pay longs.

Protocol Fees
The total amount users pay to interact with a protocol — from swaps, trades, borrowing, and other on-chain activities. Computed from protocol fee schedules applied to on-chain transaction data.

Protocol Revenue
The portion of fees retained by the protocol after payments to liquidity providers and other network participants. Holder revenue is the share distributed to token holders.

Calculation Methods
Aggregate metrics are computed by summing per-protocol and per-chain values, then normalizing to USD. Market share is calculated as a protocol's metric value divided by the total across all tracked protocols. Funding rate comparisons use the most recent funding rate event from each protocol. Historical trends are computed from time-series snapshots stored at each revalidation interval.

Missing Data
When a protocol does not expose a specific metric via its API, CoinDuck displays a dash or 'N/A' for that data point rather than estimating. In some cases, partial data may be available if a protocol exposes some but not all metrics. The dashboard clearly labels which metrics are unavailable for each protocol. If you notice consistently missing data for a protocol you use, please contact us so we can investigate the API.

Protocol Coverage
CoinDuck currently tracks Hyperliquid, Aster, Lighter, and Variational Omni as primary ecosystems, with additional DEX and DeFi protocols covered in the volume, TVL, and fees dashboards. New protocols are added based on user demand and API availability. Each protocol page shows the specific data points available for that ecosystem.

