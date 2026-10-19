## Trace Spds144A: Securitized Products Dissemination Service for 144A Transactions

Trace-based trade dissemination service publishing real-time securitized product transaction reports for asset backed securities effected under Securities Act Rule 144A and collected under Finra Rule 6700 through the Trade Reporting And Compliance Engine.

### Overview

The Securitized Products Dissemination Service for 144A Transactions (Spds-144A) is the Finra market data feed that distributes real-time trade reports for Trace eligible asset backed securities effected pursuant to Rule 144A under the Securities Act of 1933. Rule 144A permits the resale of restricted securities to qualified institutional buyers without registration, and Finra disseminates those transactions on a dedicated channel separate from Spds under Rule Filing Sr-Finra-2013-046. Of the securitized product sub products subject to dissemination, only Abs securities may be identified as Rule 144A securities.

Spds-144A is distributed in addition to, and not as a replacement of, the Spds feed for securitized products data. Because it is a separate product, vendors must subscribe to receive it regardless of whether they already take Btds or Atds. It carries the same message structure and delivery as the Bond Trade Dissemination Service and the Agency Debt Trade Dissemination Service, and its message formats are those of Spds without the parallel Mbs set, since specified pool transactions are not Rule 144A securities.

The feed uses the Data Feed Interface (Dfi) message format delivered over MoldUdp64 multicast. Every message opens with a twenty four byte header carrying the message category, message type, trade identifier, market center originator and a fourteen byte Eastern Time date and time stamp. Trade, administrative and control message categories carry trade reports, cancels and corrections, daily trade summaries, trading halts and the control messages that frame each operational cycle. The service originates from Nasdaq data centers in the New York and Mid-Atlantic areas, each providing back-up capability for the other.

### Transport

Non-interactive simplex Ip multicast over MoldUdp64, broadcast as primary and back-up groups from the New York Metro and Mid-Atlantic Metro data centers on a dedicated channel capped at 56 kilobits per second, with sequencing, gap detection and retransmission delegated to the MoldUdp64 protocol.

### Key Characteristics

- **Rule 144A securitized product trade reports** - Real-time transparency data for United States asset backed security transactions executed under Securities Act Rule 144A
- **Trace backed** - Trades sourced from the Finra Trade Reporting And Compliance Engine
- **Qualified institutional buyers** - Covers restricted securities resold to qualified institutional buyers rather than registered public issues
- **Abs and Cmo only** - Sub-Product Type is limited to Abs and Cmo, so the feed carries no Tba or Mbs message set and no Reference Data Identifier
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Dfi encoded** - Finra Data Feed Interface fixed width Ascii message format
- **Dedicated channel** - Separately subscribed feed carried alongside Spds rather than replacing it
- **Trade lifecycle** - Submission, cancellation, correction, and administrative events

