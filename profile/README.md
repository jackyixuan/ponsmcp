# PonsMCP

**Autonomous AI Agent Payments on the Machine Payments Protocol (MPP) — settled on Robinhood Chain**

$PONS CA (Robinhood Chain, chainId 4663): `0x39dBED3a2bd333467115dE45665cC57F813C4571`

---

## Overview

PonsMCP is an integration layer that enables AI agents to execute autonomous transactions using [Stripe's Machine Payments Protocol (MPP)](https://stripe.com/blog/machine-payments-protocol), with all transactions transparently settled on-chain via the **Robinhood Chain** (EVM L2, Arbitrum Orbit, chainId 4663).

By bridging natural language agent instructions with protocol-compliant stablecoin payments (USDG), PonsMCP transforms AI agents into first-class economic actors capable of discovering, negotiating, and paying for services without human intervention.

### Key Features

- **MPP Protocol Compliant** — Full support for Stripe's Machine Payments Protocol
- **Robinhood Chain Settlement** — EVM L2 (Arbitrum Orbit), gas in ETH, USDG stablecoin settlement
- **OpenClaw Integration** — First-class support for OpenClaw AI agents
- **Transparent & Auditable** — All transactions verifiable on-chain
- **Developer-First** — Ship autonomous payments in minutes, not weeks

---

## Repositories

### Core Infrastructure

#### [`ponsmcp-sdk`](https://github.com/jackyixuan/ponsmcp-sdk)

TypeScript SDK for integrating PonsMCP payments into AI agents and applications.

**Key Features:**
- Intent-based payment API
- Automatic MPP negotiation
- Robinhood Chain wallet integration
- Configurable spending policies

**Quick Start:**

```ts
import { PonsMCPClient } from '@ponsmcp/sdk'

const client = new PonsMCPClient({
  rpcUrl: 'https://rpc.mainnet.chain.robinhood.com',
  wallet: await loadAgentWallet(),
  policies: {
    maxPerTransaction: 100_000_000, // 100 USDG (6 decimals)
    dailyLimit: 1_000_000_000       // 1000 USDG
  }
})

// Agent encounters HTTP 402 — pay automatically
const result = await client.payForResource({
  url: 'https://api.weather.com/premium/forecast',
  parameters: { location: 'SF', days: 7 }
})

console.log(`Payment finalized: ${result.hash}`)
```

#### [`ponsmcp-contracts`](https://github.com/jackyixuan/ponsmcp-contracts)

EVM smart contracts for PonsMCP payment escrow and settlement on Robinhood Chain.

#### [`ponsmcp-openclaw`](https://github.com/jackyixuan/ponsmcp-openclaw)

Python integration enabling OpenClaw AI agents to make autonomous MPP payments settled on Robinhood Chain.

#### [`ponsmcp-docs`](https://github.com/jackyixuan/ponsmcp-docs)

Official documentation for the PonsMCP protocol stack.

#### [`ponsmcp-presentation`](https://github.com/jackyixuan/ponsmcp-presentation)

Official website & presentation layer — live at [pons-mcp.pages.dev](https://pons-mcp.pages.dev).

---

> Community project built on Robinhood Chain. Not affiliated with Robinhood Markets.
