# 💰 Financial Services & Wealth

## Overview

MoMo's Financial Services enables users to build wealth through accessible investment, insurance, and lending products with AI-powered guidance.

---

## Financial Services Ecosystem

```mermaid
graph TB
    subgraph "Investment Products"
        I1["📈 Mutual Funds<br/>- 100+ Fund Options<br/>- Starting 10,000₫<br/>- Auto-rebalance"]
        I2["📊 Stocks<br/>- Vietnam Market<br/>- International Stocks<br/>- Fractional Shares"]
        I3["💎 Bonds<br/>- Government Bonds<br/>- Corporate Bonds<br/>- Fixed Income"]
    end

    subgraph "Insurance Products"
        IN1["🚗 Auto Insurance<br/>- Comprehensive<br/>- Third-party<br/>- Quick Claims"]
        IN2["🏥 Health Insurance<br/>- Individual Plans<br/>- Family Plans<br/>- Wellness"]
        IN3["🏠 Property Insurance<br/>- Home Coverage<br/>- Contents<br/>- Liability"]
    end

    subgraph "Credit & Lending"
        L1["💸 Quick Loans<br/>- 1M-30M₫<br/>- 5 min approval<br/>- Flexible terms"]
        L2["🏪 Merchant Loans<br/>- Business Capital<br/>- Seasonal Financing<br/>- Growth Loans"]
        L3["💼 CreditTech<br/>- AI Underwriting<br/>- Instant Decision<br/>- Smart Pricing"]
    end

    subgraph "Tools & Support"
        T1["💻 Dashboard<br/>- Portfolio View<br/>- Performance Track<br/>- Allocation"]
        T2["🤖 AI Advisor<br/>- Smart Recommendations<br/>- Risk Assessment<br/>- Financial Planning"]
        T3["📚 Education<br/>- Investment 101<br/>- Webinars<br/>- Market Insights"]
    end

    I1 --> T1
    I2 --> T1
    I3 --> T1
    IN1 --> T1
    IN2 --> T1
    IN3 --> T1
    L1 --> T1
    L2 --> T1
    L3 --> T1

    T1 --> T2
    T1 --> T3

    style I1 fill:#FF9800,color:#fff
    style I2 fill:#FF9800,color:#fff
    style I3 fill:#FF9800,color:#fff
    style IN1 fill:#2196F3,color:#fff
    style IN2 fill:#2196F3,color:#fff
    style IN3 fill:#2196F3,color:#fff
    style L1 fill:#4CAF50,color:#fff
    style L2 fill:#4CAF50,color:#fff
    style L3 fill:#4CAF50,color:#fff
    style T1 fill:#9C27B0,color:#fff
    style T2 fill:#9C27B0,color:#fff
    style T3 fill:#9C27B0,color:#fff
```

---

## Investment Platform Architecture

```mermaid
sequenceDiagram
    participant User
    participant App
    participant AIAdvisor
    participant Portfolio
    participant Market
    participant Settlement

    User ->> App: Browse Funds
    App ->> AIAdvisor: Get Recommendations
    AIAdvisor ->> Portfolio: Check Risk Profile
    AIAdvisor -->> App: Personalized Suggestions
    
    User ->> App: Buy Fund
    App ->> Market: Check Price
    Market -->> App: Current Price
    App ->> Settlement: Execute Order
    Settlement ->> Market: Place Order
    Market -->> Settlement: Confirmed
    Settlement ->> Portfolio: Update Holdings
    Portfolio -->> App: Confirmation + Receipt
    App -->> User: Investment Successful ✓

    Note over AIAdvisor: Uses LLM for<br/>Natural Language Guidance
```

---

## Core Investment Products

### 💼 Mutual Funds
- **Options**: 100+ funds across categories
- **Min Investment**: 10,000₫ (lowest in market)
- **Categories**: Stocks, Bonds, Money Market, Balanced
- **Features**: Auto-rebalance, SIP (Systematic Investment Plan), Auto-dividend

### 📈 Stocks & Equities
- Direct access to Vietnam stock market
- Fractional share ownership
- International stocks (coming 2026)
- Real-time quotes and alerts

### 💎 Fixed Income
- Government bonds (secure returns)
- Corporate bonds (higher yield)
- Bond funds for diversification
- Ladder strategy tools

---

## Insurance Product Stack

```mermaid
graph TB
    subgraph "Auto Insurance"
        A1["Comprehensive Coverage<br/>- Third-party injury<br/>- Property damage<br/>- Own vehicle"]
        A2["Quick Claims<br/>- Photo claim<br/>- Instant payout<br/>- 24/7 support"]
        A3["Smart Pricing<br/>- Usage-based<br/>- Safe driver rewards<br/>- AI risk model"]
    end

    subgraph "Health Insurance"
        H1["Individual Plans<br/>- Hospitalization<br/>- Outpatient care<br/>- Wellness"]
        H2["Family Plans<br/>- Coverage for all<br/>- Children benefits<br/>- Maternity"]
        H3["Wellness Features<br/>- Telemedicine<br/>- Preventive care<br/>- Health tracking"]
    end

    subgraph "Property Insurance"
        P1["Home Coverage<br/>- Structure<br/>- Contents<br/>- Liability"]
        P2["Business Insurance<br/>- Inventory<br/>- Equipment<br/>- Liability"]
        P3["Specialty<br/>- Travel<br/>- Pet<br/>- Gadget"]
    end

    A1 --> A2
    H1 --> H2
    P1 --> P2

    style A1 fill:#2196F3,color:#fff
    style A2 fill:#2196F3,color:#fff
    style A3 fill:#2196F3,color:#fff
    style H1 fill:#4CAF50,color:#fff
    style H2 fill:#4CAF50,color:#fff
    style H3 fill:#4CAF50,color:#fff
    style P1 fill:#FF9800,color:#fff
    style P2 fill:#FF9800,color:#fff
    style P3 fill:#FF9800,color:#fff
```

---

## Lending & Credit Products

### 💸 Quick Loans
- **Amount**: 1M - 30M₫
- **Approval**: 5 minutes
- **Terms**: 1-24 months
- **Rate**: From 7.5% p.a.
- **Use Case**: Emergency funds, personal needs

### 🏪 Merchant Loans
- **Amount**: 5M - 500M₫
- **For**: Small business growth
- **Term**: 3-36 months
- **Process**: AI underwriting, same-day disbursement

### 🤖 CreditTech Platform
- AI-powered credit scoring
- Real-time underwriting
- Instantaneous approval
- Dynamic pricing based on risk

---

## Financial Dashboard User Journey

```mermaid
graph LR
    A["📊 Open Dashboard"] -->|"< 300ms"| B["💰 Portfolio Summary<br/>Total Assets<br/>Allocation %<br/>Performance"]
    B -->|"Tap Asset"| C["📈 Asset Details<br/>Price Chart<br/>Holdings<br/>Transactions"]
    C -->|"Tap Buy"| D["🤖 AI Suggestions<br/>Risk-adjusted<br/>Diversification<br/>Recommendations"]
    D -->|"Confirm"| E["✅ Order Placed<br/>Receipt<br/>Confirmation"]
    E -->|"Track"| F["📊 Updated Holdings<br/>Real-time P&L<br/>Performance"]

    style A fill:#FFC107,color:#000
    style B fill:#9C27B0,color:#fff
    style C fill:#9C27B0,color:#fff
    style D fill:#2196F3,color:#fff
    style E fill:#4CAF50,color:#fff
    style F fill:#9C27B0,color:#fff
```

---

## AI-Powered Features

### 🤖 Smart Advisor
- Personalized recommendations based on:
  - Risk profile
  - Investment goals
  - Time horizon
  - Market conditions
- Natural language chat interface
- Educational content

### 📊 Automated Rebalancing
- Portfolio drift detection
- Optimal rebalancing suggestions
- Automatic tax-loss harvesting (coming 2026)
- Goal tracking

### 💡 Insights Engine
- Market analysis summaries
- Fund performance rankings
- Economic indicators
- Peer comparison

---

## Key Metrics & KPIs

| Metric | 2024 Target | 2025 Target | Owner |
|--------|------------|-----------|-------|
| Investment Platform MAU | 2M | 5M | Head of Product |
| AUM (Assets Under Management) | $1.5B | $3B | CRO |
| Avg. Customer AUM | $300 | $600 | Product |
| Fund Adoption Rate | 20% | 35% | Growth |
| Insurance Premium | $50M | $120M | Insurance Lead |
| Loan Book | $500M | $1.2B | CreditTech Head |
| Customer NPS | 42 | 48 | Product |

---

## Competitive Advantages

```mermaid
graph TB
    subgraph "MoMo Advantages"
        A["✅ Lowest Min Investment<br/>10,000₫ vs competitors 100K₫"]
        B["✅ Integrated Ecosystem<br/>Pay + Invest in one app"]
        C["✅ AI-Powered Guidance<br/>Smart recommendations"]
        D["✅ Fast Onboarding<br/>< 5 min vs bank 1+ hour"]
    end

    subgraph "Market Position"
        E["🥇 #1 in Fintech Innovation"]
        F["🥇 #1 in User Accessibility"]
        G["🥇 #1 in AI Integration"]
    end

    A --> E
    B --> E
    C --> F
    D --> G

    style A fill:#4CAF50,color:#fff
    style B fill:#4CAF50,color:#fff
    style C fill:#4CAF50,color:#fff
    style D fill:#4CAF50,color:#fff
    style E fill:#FF1744,color:#fff,stroke:#C00,stroke-width:2px
    style F fill:#FF1744,color:#fff,stroke:#C00,stroke-width:2px
    style G fill:#FF1744,color:#fff,stroke:#C00,stroke-width:2px
```

---

## 2025-2026 Roadmap

**Q1 2025**: International stock expansion, Crypto gateway
**Q2 2025**: Insurance product launch, CreditTech scale
**Q3 2025**: Wealth planning tools, Automated rebalancing
**Q4 2025**: AI financial advisor, Tax optimization
**2026**: Comprehensive wealth platform, Global integration

---

## Related Documentation

- [Payment Services](./payments.md)
- [Business Solutions](./business-solutions.md)
- [Growth & Discovery](./growth-discovery.md)
- [Security & Compliance](./security-compliance.md)

---

**Last Updated**: July 2026 | **Owner**: Head of CreditTech Product
