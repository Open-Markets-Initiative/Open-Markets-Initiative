## IceFutures Bgw: IceFutures Derivatives Trading Platform Sbe Order Entry

Sbe-encoded binary order entry protocol for submitting, modifying, and cancelling orders for futures, options, and strategy markets across the Ice Derivatives Trading Platform exchange silos (Ice, Liffe, Endex). Clients first connect to the Binary Utility Service Gateway (Bus) to obtain Ip, port, and session token, then establish a Tcp session to a Binary Order Gateway (Bgw).

### Overview

The Binary Order Gateway is Ice's Sbe-based order entry channel for the Derivatives Trading Platform, providing members with a low-latency Tcp interface to submit, modify, and cancel orders for futures, options, and strategy markets across the Ice (Chicago), Liffe (Basildon), and Endex (Chicago) exchange silos. Each silo runs an independent pool of Bgws on identical hardware, so clients establish and maintain connections per silo based on their market and trading preferences.

Connecting requires a two-step handshake. First, the client connects to the Binary Utility Service Gateway (Bus) and submits an IpRequest for one or more Gateway IDs; Bus assigns each Gateway ID to a Bgw via round-robin and returns Ip, port, and session token in the IpReport response, valid only for the current trading session. Second, the client opens a Tcp connection to the assigned Bgw and sends LogonRequest with the issued token. A single Gateway ID can concurrently be logged into Fix OS, Bus, and Bgw within an exchange silo; duplicate logons or logons with mismatched credentials are rejected.

Once logged in, clients log Trader IDs via TraderLogonRequest to receive open Gtc/Gtd order state plus any fills or cancels that occurred while the Trader ID was logged out (Wywo) and the last 60 seconds of the previous session. Heartbeats run every 30 seconds (1-second minimum, configurable on logon). Outbound sequence numbers reset to 1 at the start of each trading session and continue across mid-session reconnects; inbound sequences from clients are advisory unless a decode failure occurs. Application-level messages can be retransmitted via ResendRequest with start/end sequence numbers. Tcp disconnect or LogoutRequest cancels all open non-Gtc/Gtd orders for that Bgw session — cancel-on-disconnect is default behavior and not configurable.

### Transport

Tcp/Ip session carrying Sbe-encoded session and application messages — logon, heartbeat, sequence and resend, order new/cancel/replace, mass quote, mass action, execution report, and reference data requests. Session credentials (Ip, port, token) are issued per Gateway ID by the Binary Utility Service Gateway (Bus) for each exchange trading session.

### Key Characteristics

- **Ice Derivatives Trading Platform** - Order entry for futures, options, and strategies across Ice global derivatives venues
- **Sbe encoded** - Fix Simple Binary Encoding for fixed-width low-latency wire format
- **Two-step Bus handshake** - Binary Utility Service Gateway issues per-session Ip, port, and token before Bgw connect
- **Round-robin Gateway assignment** - Bus load-balances Gateway IDs across the Bgw pool within each exchange silo
- **Three exchange silos** - Independent Ice, Liffe, and Endex environments with identical hardware specifications
- **Trader logon and Wywo** - TraderLogonRequest delivers open Gtc/Gtd state and Wywo activity from the prior session
- **Heartbeats and resend** - 30-second default heartbeat (1-second minimum) with ResendRequest for application-level message recovery
- **Cancel on disconnect** - Tcp disconnect or LogoutRequest cancels open non-Gtc/Gtd orders for the Bgw session
- **Throttle limits** - Default 300 msgs/sec for new orders and cancel/replace, 1000 msgs/sec for mass quote cancels, configurable per Gateway ID

