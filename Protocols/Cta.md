## CTA: Consolidated Tape Association

The Consolidated Tape Association oversees the dissemination of real-time trade and quote data for exchange-listed equity securities in the United States, operated by SIAC (Securities Industry Automation Corporation) as the exclusive Securities Information Processor.

### Overview

The CTA Plan was established under the Securities Exchange Act of 1934 to ensure investors have access to a consolidated view of trading activity across all national securities exchanges. CTA operates two primary data feeds: CTS (Consolidated Tape System) for last sale trade reports and CQS (Consolidated Quotation System) for best bid and offer quotes. The plan is divided into Network A for NYSE-listed securities (Tape A), and Network B for NYSE American and regional exchange-listed securities (Tape B). A separate but related plan, the UTP Plan administered by Nasdaq, covers Nasdaq-listed securities (Tape C).

CTS receives last sale trade reports from all participating market centers and disseminates them in a consolidated stream. CQS collects and distributes the best bid and offer quotation information from each exchange, enabling subscribers to see the National Best Bid and Offer (NBBO) across all venues. Together, these feeds form the backbone of the US equity consolidated tape mandated by the SEC under Regulation NMS.

Current participants include NYSE, NYSE American, NYSE Arca, NYSE National, NYSE Texas, Nasdaq, Nasdaq BX, Nasdaq PHLX, Nasdaq ISE, Cboe BZX, Cboe BYX, Cboe EDGA, Cboe EDGX, IEX, MEMX, MIAX Pearl, LTSE, 24X National Exchange, and FINRA. The CTA SIP infrastructure is located in the Mahwah, New Jersey data center.

### Transport

CTS and CQS data is disseminated via IP multicast over dedicated network infrastructure. Data is transmitted as variable-length binary blocks with a maximum block size of 1,000 bytes. Each IP packet encapsulates a single transmission block consisting of a block header, block data with one or more messages, and an optional pad byte. Each message contains a fixed-length header identifying the message category and type followed by variable-length message data. TCP-based retransmission services are available for gap recovery.

### Key Characteristics

- **Consolidated national feed** - Aggregates trade and quote data from all US equity exchanges and market centers
- **Two networks** - Network A for NYSE-listed (Tape A), Network B for regional exchange-listed (Tape B)
- **Binary encoding** - Variable-length messages within fixed-maximum-size binary blocks (1,000 bytes max)
- **IP multicast distribution** - Real-time dissemination via multicast groups over dedicated infrastructure
- **Regulatory mandate** - SEC-mandated consolidated data feeds under Regulation NMS
- **SIP processing** - SIAC validates, sequences, and timestamps all incoming data before redistribution
- **Pillar platform** - Modern specifications based on the NYSE Pillar technology platform
