<div align="center">

<img src="assets/logo.jpg" alt="Fivo" width="80" />

# Fivo

**The easiest way to accept stablecoin payments.**

[![Live on Mainnet](https://img.shields.io/badge/Status-Live%20on%20Mainnet-brightgreen?style=flat-square)](https://fivo.finance)
[![Built with Circle](https://img.shields.io/badge/Built%20with-Circle-2762F8?style=flat-square&logo=circle)](https://www.circle.com/)
[![Circle Alliance](https://img.shields.io/badge/Circle-Alliance%20Member-2762F8?style=flat-square&logo=circle)](https://partners.circle.com)
[![9 Networks](https://img.shields.io/badge/Networks-9%20EVM%20Chains-blue?style=flat-square)](https://fivo.finance/chains)
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-gray?style=flat-square)](LICENSE)

Accept USDC and EURC on your website with a single line of code. No banks, no borders, no delays.

[Website](https://fivo.finance) | [Documentation](https://fivo.finance/docs) | [Quick Start](https://fivo.finance/docs/quickstart) | [Blog](https://fivo.finance/blog) | [Contact](https://fivo.finance/contact)

<img src="assets/hero.png" alt="Fivo — Stablecoin Payment Gateway" width="700" />

</div>

---

## What is Fivo?

Fivo is a stablecoin payment gateway that lets merchants accept USDC and EURC payments across 9 blockchain networks with instant settlement.

Built on [Circle](https://www.circle.com/) infrastructure (Programmable Wallets + [Bridge Kit SDK](https://developers.circle.com/w3s/bridge-kit-sdk)), Fivo handles cross-chain bridging automatically. A customer can pay from any supported network and the merchant receives funds on their preferred chain.

<div align="center">
<img src="assets/circle-alliance.png" alt="Fivo — Circle Alliance Member" width="700" />
</div>

## How It Works

<div align="center">
<table>
  <tr>
    <td align="center" width="33%">
      <strong>1. Select network</strong><br/><br/>
      <img src="assets/widget.png" alt="Fivo checkout — select network" width="220" /><br/><br/>
      <sub>Customer picks any chain.<br/>Balances shown in real time.</sub>
    </td>
    <td align="center" width="33%">
      <strong>2. Confirm payment</strong><br/><br/>
      <img src="assets/confirm-payment.png" alt="Fivo checkout — confirm cross-chain payment" width="220" /><br/><br/>
      <sub>Full fee breakdown.<br/>One-click confirmation.</sub>
    </td>
    <td align="center" width="33%">
      <strong>3. Done</strong><br/><br/>
      <img src="assets/payment-complete.png" alt="Fivo checkout — payment complete" width="220" /><br/><br/>
      <sub>Confirmed on-chain.<br/>Merchant receives instantly.</sub>
    </td>
  </tr>
</table>
</div>

## Integration

### Widget (recommended)

Add the Fivo script once and place payment buttons anywhere on your page:

```html
<script async src="https://checkout.fivo.finance/v1/fivo.js"></script>

<fivo-button
  merchant-id="your_merchant_id"
  amount="25.00"
  currency="USDC">
</fivo-button>
```

This renders a "Pay with Fivo" button that opens a checkout modal. The customer connects their wallet, selects a network, and pays. All without leaving your site.

<div align="center">
<img src="assets/shop-demo.png" alt="Fivo payment buttons integrated in an e-commerce store" width="700" />
<br/><sub>Example: Fivo payment buttons integrated in a product catalog</sub>
</div>

<br/>

For variable amounts (donations, tips), omit the `amount` attribute and the customer enters the amount themselves.

### Checkout Sessions (API)

Create a payment session server-side and redirect your customer:

```bash
curl -X POST https://api.fivo.finance/checkout/sessions \
  -H "X-API-Key: your_api_key" \
  -H "Content-Type: application/json" \
  -d '{
    "amount": "25.00",
    "currency": "USDC",
    "return_url": "https://yoursite.com/success",
    "cancel_url": "https://yoursite.com/cancel"
  }'
```

### Direct API

For full control, use the REST API to build custom payment flows. See the [API Reference](https://fivo.finance/docs/api-reference).

## Cross-Chain Payments

Customers pay from any supported network. If the merchant's wallet is on a different chain, Fivo bridges the funds automatically via [Circle Bridge Kit](https://developers.circle.com/w3s/bridge-kit-sdk), with full fee transparency before confirmation.

Bridge Kit handles the entire cross-chain flow (approve, burn, attestation, mint) in a single transaction from the customer's perspective. No intermediate wallets, no manual steps.

## Merchant Dashboard

Track payments in real time, manage wallets across chains, configure webhooks, issue refunds, and withdraw funds with automatic invoice generation.

<div align="center">
<img src="assets/dashboard.png" alt="Fivo Merchant Dashboard — payment analytics and management" width="700" />
</div>

## Demo Store

See Fivo in action on a fully working demo e-commerce site. Browse products, add to cart, and complete a real checkout flow using testnet USDC.

<div align="center">
<img src="assets/demo-site.png" alt="Fivo Demo Store — live e-commerce demo" width="700" />
<br/><sub><a href="https://demo.fivo.finance">demo.fivo.finance</a></sub>
</div>

## Supported Networks

| Network | USDC | EURC | Cross-Chain |
|---------|------|------|-------------|
| Ethereum | Yes | Yes | Bridge |
| Polygon | Yes | Yes | Bridge |
| Avalanche | Yes | Yes | Bridge |
| Arbitrum | Yes | Yes | Bridge |
| Base | Yes | Yes | Instant |
| Optimism | Yes | Yes | Bridge |
| Linea | Yes | No | Bridge |
| Unichain | Yes | No | Bridge |
| Sonic | Yes | No | Bridge |

The merchant receives on their chosen network regardless of which chain the customer pays from.

## Key Features

- **Multi-chain.** 9 EVM networks, one integration
- **Cross-chain bridging.** Automatic via Circle Bridge Kit
- **Stablecoins only.** USDC and EURC, no volatility
- **Instant settlement.** Funds arrive in your wallet, not a bank account
- **Multi-language.** Dashboard, widget, docs and emails in 5 languages (EN, ES, FR, DE, PT)
- **Customer notifications.** Payment receipts and refund confirmations sent to customers via email
- **Refunds.** On-chain refund execution with receipt PDF
- **Invoicing.** Automatic invoice per withdrawal with PDF generation
- **Webhooks.** HMAC-SHA256 signed, real-time payment notifications
- **Enterprise security.** 2FA, API key management, audit trail

## Testing

Fivo provides a full testnet environment so you can integrate and test without risking real funds.

| Service | Mainnet | Testnet |
|---------|---------|---------|
| Dashboard | [fivo.finance](https://fivo.finance) | [test.fivo.finance](https://test.fivo.finance) |
| API | api.fivo.finance | api-test.fivo.finance |
| Widget | checkout.fivo.finance | checkout-test.fivo.finance |

**How to test:**

1. Register at [test.fivo.finance](https://test.fivo.finance) — you'll get a testnet merchant ID (`fivo_test_*`)
2. Get free testnet USDC from the [Circle Faucet](https://faucet.circle.com)
3. Integrate the widget pointing to the testnet script:

```html
<script async src="https://checkout-test.fivo.finance/v1/fivo.js"></script>

<fivo-button
  merchant-id="fivo_test_your_id"
  amount="10.00"
  currency="USDC">
</fivo-button>
```

4. Make test payments, configure webhooks, and verify everything works
5. When ready, register at [fivo.finance](https://fivo.finance) to get your mainnet merchant ID (`fivo_live_*`) and go live

Both environments are fully independent with separate databases, wallets, and API keys.

## Blog

Stay up to date with product announcements, integration guides, and industry insights on the [Fivo Blog](https://fivo.finance/blog).

## Pricing

- **No monthly fees**
- **No setup costs**
- **0.5% fee on withdrawals only**
- Free account creation in 30 seconds

## Built With

- [Circle Programmable Wallets](https://www.circle.com/en/programmable-wallets). Secure wallet infrastructure
- [Circle Bridge Kit SDK](https://developers.circle.com/w3s/bridge-kit-sdk). Cross-chain USDC/EURC transfers
- [USDC](https://www.circle.com/en/usdc). Fully reserved, regulated stablecoin
- [EURC](https://www.circle.com/en/eurc). Euro-backed stablecoin by Circle

## Links

- [Website](https://fivo.finance)
- [Dashboard](https://fivo.finance/login)
- [Documentation](https://fivo.finance/docs)
- [Quick Start Guide](https://fivo.finance/docs/quickstart)
- [API Reference](https://fivo.finance/docs/api-reference)
- [Blog](https://fivo.finance/blog)
- [Demo Store](https://demo.fivo.finance)
- [Contact](https://fivo.finance/contact)

---

Copyright 2025-2026 Fivo. All rights reserved.
