## FundNetwork Data Service: NFN Data Service

Ascii market data feed disseminating net asset values, prices, yields and distributions for U.S. investment companies registered with the Nasdaq Fund Network.

### Overview

The Nasdaq Fund Network, operated by Nasdaq Information, LLC, collects price and earnings information for U.S. investment companies and disseminates it on the NFN Data Service: daily net asset values and offer or market prices for mutual funds, average maturity and 7-day yield for money market funds, offer price, net asset value and other valuation data for unit investment trusts, and periodic dividend, stock dividend and capital gains distributions.

Messages are seven bit ascii, each a 22 character header followed by a text section, carried in blocks of up to 1000 characters. Administrative, control and NFN valuation message categories cover free form text, daily statistics, the symbol directory, session and day boundaries and the valuation and distribution data.

### Transport

Non-interactive simplex IP multicast on a primary and a back-up group carrying identical messages; retransmissions are requested from Nasdaq Computer Operations by telephone or email and broadcast on both groups.

### Key Characteristics

- **Fund valuations** - Net asset values and prices for mutual funds, unit investment trusts and other fund types
- **Money market funds** - Average maturity and 7-day yield
- **Distributions** - Dividend, income and capital gains distributions
- **Primary and back-up groups** - Two multicast groups with identical messages
- **Manual retransmission** - Retransmissions requested by telephone or email by message sequence number

