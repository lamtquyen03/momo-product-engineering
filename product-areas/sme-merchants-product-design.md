# 🏪 SME Payment & Business Solutions - Product Design Guide

**Focus Area**: Merchant Engagement & Monetization  
**Product Manager Role**: Manager - New Business and Product Development (SME Merchants)  
**Market**: SMEs, Small Merchants, Household Businesses in Vietnam  
**Mission**: Build 0→1 products that help merchants go beyond payments to manage, grow, and scale their business

---

## 📋 Table of Contents

1. [Business Requirements](#business-requirements)
2. [Product Design Architecture](#product-design-architecture)
3. [Product Samples & UX/UI Artifacts](#product-samples--uxui-artifacts)
4. [Data Schema & UI Mapping](#data-schema--ui-mapping)

---

---

# 1. BUSINESS REQUIREMENTS

## 1.1 Market Opportunity & Context

```mermaid
graph TB
    subgraph "Current MoMo Position"
        A["🏪 1M+ Active Merchants"]
        B["💳 QR Payment Platform<br/>Strong PMF"]
        C["🔊 Soundbox<br/>200K devices"]
        D["📊 Transaction Data<br/>Rich behavioral insights"]
    end

    subgraph "Market Gap"
        E["❌ No sales management<br/>Merchants use paper/Excel"]
        F["❌ No customer CRM<br/>Can't track repeat buyers"]
        G["❌ No financing<br/>Lack working capital"]
        H["❌ No compliance<br/>Manual tax/invoice"]
    end

    subgraph "Competitive Threat"
        I["⚠️ Competitors replicating<br/>payments fast"]
        J["⚠️ Merchant churn risk<br/>switching to rivals"]
        K["⚠️ Commoditization<br/>of QR/hardware"]
    end

    A --> E
    B --> F
    C --> G
    D --> H
    
    E --> I
    F --> J
    G --> K
    H --> K

    style A fill:#FF1744,color:#fff
    style B fill:#FF1744,color:#fff
    style C fill:#FF1744,color:#fff
    style D fill:#FF1744,color:#fff
    style E fill:#FF9800,color:#fff
    style F fill:#FF9800,color:#fff
    style G fill:#FF9800,color:#fff
    style H fill:#FF9800,color:#fff
    style I fill:#E53935,color:#fff
    style J fill:#E53935,color:#fff
    style K fill:#E53935,color:#fff
```

## 1.2 Business Objectives (0→1 Phase)

```mermaid
graph LR
    A["🎯 Retention Moat<br/>Lock-in beyond payments<br/>+3 products = 80% LTV"] -->|"builds"| B["💰 Revenue Expansion<br/>Fintech + SaaS revenue<br/>30% incremental margin"]
    
    B -->|"drives"| C["🏆 Market Leadership<br/>MoMo = Merchant OS<br/>not just payment processor"]

    C -->|"enables"| D["🌍 Regional Expansion<br/>Repeat playbook<br/>Southeast Asia"]

    style A fill:#FF1744,color:#fff,stroke:#C00,stroke-width:2px
    style B fill:#2196F3,color:#fff
    style C fill:#4CAF50,color:#fff
    style D fill:#9C27B0,color:#fff
```

## 1.3 Merchant Personas & Pain Points

### Persona A: 🍜 Street Food Vendor

```mermaid
graph TB
    subgraph "Demographics"
        D["📍 Ho Chi Minh City<br/>💰 Daily revenue: 2-5M₫<br/>👥 Team: Self-run<br/>📱 Smartphone literate"]
    end

    subgraph "Pain Points"
        P1["📊 Can't track who buys<br/>Lost repeat customer data"]
        P2["💳 Daily cash management<br/>Worried about losses"]
        P3["📋 No business records<br/>Tax/compliance confusion"]
        P4["💸 Need short-term loan<br/>For supplies/expansion"]
    end

    subgraph "Needs"
        N1["Simple daily sales log<br/>No Excel skills needed"]
        N2["Customer phone collection<br/>For SMS promotions"]
        N3["Auto tax calculation<br/>Easy filing"]
        N4["Micro-loan: 2-5M₫<br/>5-7 days repayment"]
    end

    D --> P1
    P1 --> N1
    D --> P2
    P2 --> N2
    D --> P3
    P3 --> N3
    D --> P4
    P4 --> N4

    style D fill:#FFC107,color:#000
    style P1 fill:#FF9800,color:#fff
    style P2 fill:#FF9800,color:#fff
    style P3 fill:#FF9800,color:#fff
    style P4 fill:#FF9800,color:#fff
    style N1 fill:#4CAF50,color:#fff
    style N2 fill:#4CAF50,color:#fff
    style N3 fill:#4CAF50,color:#fff
    style N4 fill:#4CAF50,color:#fff
```

### Persona B: 🏪 Retail Shop Owner

```mermaid
graph TB
    subgraph "Demographics"
        D["📍 District 1, Ho Chi Minh<br/>💰 Daily revenue: 10-50M₫<br/>👥 Team: 2-5 staff<br/>📱 Business smartphone user"]
    end

    subgraph "Pain Points"
        P1["📊 Can't see staff performance<br/>No data on who sells most"]
        P2["💳 Complex inventory<br/>Manual stock tracking"]
        P3["📞 Customer repeat rate: 30%<br/>No loyalty program"]
        P4["💰 Growing to 5 shops<br/>Need capital + systems"]
    end

    subgraph "Needs"
        N1["Staff dashboard<br/>See daily/staff sales"]
        N2["Inventory sync<br/>QR payment + stock update"]
        N3["Loyalty program<br/>Points/rewards"]
        N4["Growth financing<br/>5-50M₫ for expansion"]
    end

    D --> P1
    P1 --> N1
    D --> P2
    P2 --> N2
    D --> P3
    P3 --> N3
    D --> P4
    P4 --> N4

    style D fill:#FFC107,color:#000
    style P1 fill:#FF9800,color:#fff
    style P2 fill:#FF9800,color:#fff
    style P3 fill:#FF9800,color:#fff
    style P4 fill:#FF9800,color:#fff
    style N1 fill:#4CAF50,color:#fff
    style N2 fill:#4CAF50,color:#fff
    style N3 fill:#4CAF50,color:#fff
    style N4 fill:#4CAF50,color:#fff
```

## 1.4 Product Portfolio Strategy (Year 1)

```mermaid
graph TB
    subgraph "Q2 2025: Merchant Dashboard"
        Q1["📊 Daily sales analytics<br/>Revenue by hour/category<br/>Top items"]
        Q1_IMPACT["→ Reduce churn: -5%<br/>→ ARPU: +2%"]
    end

    subgraph "Q3 2025: Customer Engagement"
        Q2["📱 SMS/WhatsApp marketing<br/>Build customer database<br/>Promotional campaigns"]
        Q2_IMPACT["→ Repeat rate: +25%<br/>→ GMV growth: +15%"]
    end

    subgraph "Q4 2025: Compliance & Invoicing"
        Q3["📋 Auto e-invoicing<br/>Tax calculation<br/>Regulatory reporting"]
        Q3_IMPACT["→ Compliance adoption: 40%<br/>→ Trust score: +10%"]
    end

    subgraph "Q1 2026: Merchant Financing"
        Q4["💰 Quick loans<br/>Working capital<br/>Growth financing"]
        Q4_IMPACT["→ New revenue: $5M<br/>→ LTV: +40%"]
    end

    Q1 --> Q1_IMPACT
    Q1_IMPACT -->|"success"| Q2
    Q2 --> Q2_IMPACT
    Q2_IMPACT -->|"success"| Q3
    Q3 --> Q3_IMPACT
    Q3_IMPACT -->|"success"| Q4
    Q4 --> Q4_IMPACT

    style Q1 fill:#2196F3,color:#fff
    style Q2 fill:#00BCD4,color:#000
    style Q3 fill:#4CAF50,color:#fff
    style Q4 fill:#FF1744,color:#fff
    style Q1_IMPACT fill:#2196F3,color:#fff,stroke:#0D47A1,stroke-width:2px
    style Q2_IMPACT fill:#00BCD4,color:#000,stroke:#00838F,stroke-width:2px
    style Q3_IMPACT fill:#4CAF50,color:#fff,stroke:#1B5E20,stroke-width:2px
    style Q4_IMPACT fill:#FF1744,color:#fff,stroke:#C00,stroke-width:2px
```

## 1.5 Success Metrics & Business KPIs

### Tier 1: Retention & Engagement

| Metric | Baseline 2024 | Q4 2025 Target | 2026 Target | Why It Matters |
|--------|--------------|----------------|------------|----------------|
| Merchant Churn | 25% annual | 20% | 15% | Core survival metric |
| Engaged Merchants (using 2+ features) | 30% | 55% | 75% | Cross-sell success |
| Avg Revenue per Merchant | $200/year | $350/year | $600/year | Monetization |
| Merchant NPS | 42 | 50 | 55 | Loyalty & advocacy |

### Tier 2: Product Adoption

| Metric | Q1 Launch | Q2 | Q3 | Q4 |
|--------|-----------|----|----|-----|
| Dashboard Adoption | 20% | 35% | 50% | 65% |
| SMS Campaign MAU | 5% | 12% | 25% | 40% |
| E-Invoice Adoption | - | - | 15% | 35% |
| Loan Applications | - | - | - | 5% |

### Tier 3: Revenue & Profitability

| Product | Year 1 Revenue Target | Gross Margin | Strategy |
|---------|--------|---------|----------|
| Dashboard (SaaS) | $800K | 75% | Freemium + premium |
| SMS Marketing | $1.2M | 70% | Pay-per-campaign |
| E-Invoice & Tax | $500K | 80% | Per-filing fee |
| Merchant Loans | $5M | 15% | Interest + fees |

---

---

# 2. PRODUCT DESIGN ARCHITECTURE

## 2.1 Merchant Ecosystem Map

```mermaid
graph TB
    subgraph "Merchant Core"
        M["🏪 Merchant Profile<br/>- KYC info<br/>- Business details<br/>- Settlement account"]
    end

    subgraph "Payment Layer"
        P1["💳 QR Payment<br/>Existing strength"]
        P2["💾 Settlement<br/>Daily settlement"]
        P3["📊 Payment Analytics<br/>Transaction data"]
    end

    subgraph "Business Operations"
        B1["📊 Dashboard<br/>Sales analytics<br/>Performance tracking"]
        B2["📦 Inventory<br/>Stock management<br/>Low stock alerts"]
        B3["📝 Invoicing<br/>E-invoices<br/>Tax compliance"]
    end

    subgraph "Engagement & Growth"
        G1["📱 Customer DB<br/>Phone/email collection<br/>Repeat customer tracking"]
        G2["📢 Marketing<br/>SMS campaigns<br/>Promotions"]
        G3["🎁 Loyalty<br/>Points program<br/>Rewards"]
    end

    subgraph "Financial Services"
        F1["💰 Loans<br/>Working capital<br/>Growth financing"]
        F2["💳 PayLater<br/>Merchant credit<br/>Inventory financing"]
        F3["📈 Insurance<br/>Business insurance<br/>Liability"]
    end

    M --> P1
    P1 --> P2
    P2 --> P3
    
    P3 --> B1
    P3 --> B2
    P3 --> B3
    
    B1 --> G1
    G1 --> G2
    G1 --> G3
    
    P3 --> F1
    B1 --> F1
    P1 --> F2

    style M fill:#FF1744,color:#fff,stroke:#C00,stroke-width:3px
    style P1 fill:#2196F3,color:#fff
    style P2 fill:#2196F3,color:#fff
    style P3 fill:#2196F3,color:#fff
    style B1 fill:#4CAF50,color:#fff
    style B2 fill:#4CAF50,color:#fff
    style B3 fill:#4CAF50,color:#fff
    style G1 fill:#9C27B0,color:#fff
    style G2 fill:#9C27B0,color:#fff
    style G3 fill:#9C27B0,color:#fff
    style F1 fill:#FF9800,color:#fff
    style F2 fill:#FF9800,color:#fff
    style F3 fill:#FF9800,color:#fff
```

## 2.2 Product 1: Merchant Dashboard (Q2 2025)

### 2.2.1 Problem & Solution

```mermaid
graph LR
    A["Problem:<br/>Merchants use Excel<br/>manually track sales<br/>Can't see trends"] -->|"Solution"| B["Dashboard:<br/>Auto-synced from QR<br/>Real-time analytics<br/>Trend insights"]
    
    B -->|"Outcome"| C["Result:<br/>Better decisions<br/>Inventory optimization<br/>Staff management"]

    style A fill:#FF9800,color:#fff
    style B fill:#4CAF50,color:#fff,stroke:#1B5E20,stroke-width:2px
    style C fill:#2196F3,color:#fff
```

### 2.2.2 Feature Breakdown

```mermaid
graph TB
    subgraph "Dashboard Home"
        H1["📊 At-a-glance KPIs<br/>- Today revenue<br/>- vs Yesterday<br/>- vs This week<br/>- vs Last month"]
        H2["🎯 Daily Target<br/>- Target: 5M₫<br/>- Actual: 4.2M₫<br/>- Status: 84%"]
        H3["📈 Trend Chart<br/>- Last 7 days<br/>- Last 30 days<br/>- Interactive graph"]
    end

    subgraph "Detailed Analytics"
        A1["🕐 By Time<br/>- Hourly breakdown<br/>- Peak hours<br/>- Slow periods"]
        A2["🛍️ By Category<br/>- Item-level sales<br/>- Category trends<br/>- Popular items"]
        A3["💳 By Payment<br/>- QR vs Cash<br/>- Payment method split<br/>- Conversion rate"]
    end

    subgraph "Business Insights"
        I1["👥 Customer Insights<br/>- Repeat rate: 35%<br/>- Avg purchase: 50K<br/>- Top customers"]
        I2["💡 Recommendations<br/>- Stock low item Y<br/>- Promote item Z<br/>- Schedule sale for Wed"]
        I3["📊 Benchmarks<br/>- vs similar shops<br/>- vs your history<br/>- Industry average"]
    end

    H1 --> A1
    H2 --> A2
    H3 --> A3
    
    A1 --> I1
    A2 --> I2
    A3 --> I3

    style H1 fill:#2196F3,color:#fff
    style H2 fill:#2196F3,color:#fff
    style H3 fill:#2196F3,color:#fff
    style A1 fill:#00BCD4,color:#000
    style A2 fill:#00BCD4,color:#000
    style A3 fill:#00BCD4,color:#000
    style I1 fill:#4CAF50,color:#fff
    style I2 fill:#4CAF50,color:#fff
    style I3 fill:#4CAF50,color:#fff
```

### 2.2.3 Data Flow: QR Payment → Dashboard

```mermaid
sequenceDiagram
    participant QR as QR Payment<br/>Terminal
    participant Backend as MoMo Backend<br/>Processing
    participant ETL as ETL Pipeline<br/>Data Sync
    participant DB as Analytics DB<br/>Data Warehouse
    participant Dashboard as Merchant<br/>Dashboard

    QR ->> Backend: Transaction event
    activate Backend
    Backend ->> Backend: Validate + Process
    Backend ->> ETL: Send to pipeline
    deactivate Backend

    activate ETL
    ETL ->> ETL: Transform + Aggregate
    ETL ->> DB: Insert analytics data
    deactivate ETL

    activate DB
    DB ->> Dashboard: Real-time data stream
    deactivate DB

    Dashboard ->> Dashboard: Render charts
    Dashboard -->> Merchant: Display dashboard ✓

    Note over QR,Dashboard: Latency: < 1 minute<br/>for < 1M merchants<br/>< 5 minutes for all
```

## 2.3 Product 2: Customer Engagement Platform (Q3 2025)

### 2.3.1 Architecture

```mermaid
graph TB
    subgraph "Data Collection"
        D1["🔗 Link QR Payment<br/>Capture phone numbers<br/>Each transaction"]
        D2["📱 Manual Entry<br/>Merchant adds customers<br/>Import from Excel"]
        D3["🤖 AI Enrichment<br/>Segment customers<br/>Predict behavior"]
    end

    subgraph "Customer Database"
        DB["📊 Customer DB<br/>- Phone<br/>- Purchase history<br/>- Frequency<br/>- Total spend<br/>- Tags/segments"]
    end

    subgraph "Engagement Channels"
        SMS["📬 SMS Campaign<br/>Send promotions<br/>Track opens/clicks"]
        WA["💬 WhatsApp<br/>Direct messaging<br/>Customer service"]
        EMAIL["📧 Email<br/>Newsletters<br/>Offers"]
    end

    subgraph "Analytics"
        ANALYTICS["📈 Campaign Analytics<br/>- Sent count<br/>- Open rate<br/>- Click rate<br/>- Conversion rate<br/>- ROI"]
    end

    D1 --> DB
    D2 --> DB
    D3 --> DB

    DB --> SMS
    DB --> WA
    DB --> EMAIL

    SMS --> ANALYTICS
    WA --> ANALYTICS
    EMAIL --> ANALYTICS

    style D1 fill:#2196F3,color:#fff
    style D2 fill:#2196F3,color:#fff
    style D3 fill:#2196F3,color:#fff
    style DB fill:#FF1744,color:#fff,stroke:#C00,stroke-width:3px
    style SMS fill:#4CAF50,color:#fff
    style WA fill:#4CAF50,color:#fff
    style EMAIL fill:#4CAF50,color:#fff
    style ANALYTICS fill:#9C27B0,color:#fff
```

### 2.3.2 Features & Use Cases

```mermaid
graph LR
    A["🎯 Segment Customers<br/>By: Frequency, Spend,<br/>Last purchase, Tags"] -->|"1"| B1["📢 Send SMS<br/>'Come back sale'<br/>Discount code"]
    
    A -->|"2"| B2["💬 WhatsApp<br/>Personalized offer<br/>based on purchase"]
    
    A -->|"3"| B3["🎁 Loyalty Rewards<br/>100 points<br/>after 5 visits"]

    B1 -->|"Result"| C1["📊 15% open<br/>8% click<br/>3% conversion"]
    B2 -->|"Result"| C2["📊 30% read<br/>12% reply<br/>5% purchase"]
    B3 -->|"Result"| C3["📊 Repeat +20%<br/>Lifetime value<br/>+25%"]

    style A fill:#FFC107,color:#000,stroke:#FFA000,stroke-width:2px
    style B1 fill:#2196F3,color:#fff
    style B2 fill:#2196F3,color:#fff
    style B3 fill:#2196F3,color:#fff
    style C1 fill:#4CAF50,color:#fff
    style C2 fill:#4CAF50,color:#fff
    style C3 fill:#4CAF50,color:#fff
```

## 2.4 Product 3: E-Invoice & Compliance (Q4 2025)

### 2.4.1 Problem & Solution

```mermaid
graph TB
    subgraph "Current State"
        P1["❌ Manual invoices<br/>Paper or Word doc"]
        P2["❌ No tax tracking<br/>Guess when filing"]
        P3["❌ Audit risk<br/>No records"]
        P4["❌ Compliance confusion<br/>Regulatory uncertainty"]
    end

    subgraph "MoMo Solution"
        S1["✅ Auto e-invoices<br/>Generated from QR txns<br/>Compliant format"]
        S2["✅ Tax calculation<br/>Auto-calc VAT/taxes<br/>Based on category"]
        S3["✅ Audit trail<br/>All txns recorded<br/>Time-stamped"]
        S4["✅ Compliance help<br/>Filing assistant<br/>Regulatory guide"]
    end

    P1 --> S1
    P2 --> S2
    P3 --> S3
    P4 --> S4

    style P1 fill:#FF9800,color:#fff
    style P2 fill:#FF9800,color:#fff
    style P3 fill:#FF9800,color:#fff
    style P4 fill:#FF9800,color:#fff
    style S1 fill:#4CAF50,color:#fff
    style S2 fill:#4CAF50,color:#fff
    style S3 fill:#4CAF50,color:#fff
    style S4 fill:#4CAF50,color:#fff
```

### 2.4.2 Workflow: Auto E-Invoice Generation

```mermaid
sequenceDiagram
    participant Merchant as Merchant<br/>Soundbox
    participant QR as QR<br/>Transaction
    participant System as Invoice<br/>System
    participant Tax as Tax<br/>Engine
    participant Archive as Invoice<br/>Archive
    participant Gov as Govt DB<br/>eInvoice Portal

    Merchant ->> QR: Customer pays 100K
    QR ->> System: Transaction logged
    System ->> Tax: Calculate tax (10% = 10K)
    Tax -->> System: Tax amount
    System ->> System: Generate invoice<br/>Invoice #MOM001<br/>Datetime<br/>Items<br/>Total
    System ->> Archive: Store in archive
    Archive ->> Gov: Auto-submit to<br/>eInvoice portal
    Gov -->> System: Confirmed receipt ✓
    System ->> Merchant: Invoice ready<br/>Send to customer

    Note over System,Archive: Instant - < 5 sec<br/>No merchant action needed
```

---

---

# 3. PRODUCT SAMPLES & UX/UI ARTIFACTS

## 3.1 Merchant Dashboard - UI Wireframe

### Home Screen

```
┌───────────────────────────────────────┐
│          🏪 Merchant Dashboard         │
│                                       │
├─ TODAY ─────────────────────────────┤
│                                       │
│  💰 Revenue Today        📊 Target    │
│  ┌─────────────────────┐ ┌─────────┐ │
│  │     4.2M ₫          │ │ 84% 🟢  │ │
│  │   vs Yest: +150K ↑  │ │ 5M ₫    │ │
│  └─────────────────────┘ └─────────┘ │
│                                       │
│  📈 Last 7 Days Revenue               │
│  ┌─────────────────────────────────┐ │
│  │     ╱╲   ╱╲                      │ │
│  │    ╱  ╲ ╱  ╲  ╱╲   ╱╲           │ │
│  │   ╱    ╱     ╲╱  ╲╱   ╲        │ │
│  │  Mon Tue Wed Thu Fri Sat Sun    │ │
│  │  3.2  3.8  4.1  3.9  4.5 4.2 M₫│ │
│  └─────────────────────────────────┘ │
│                                       │
├─ BREAKDOWN ──────────────────────────┤
│                                       │
│  🕐 By Hour       🛍️ By Category     │
│  ├─ 9-10am: 800K   ├─ Bún phở: 1.8M  │
│  ├─ 10-11am: 900K  ├─ Egg roll: 900K │
│  ├─ 11-12: 1.2M    ├─ Soup: 600K     │
│  ├─ 12-1pm: 800K   └─ Drink: 300K    │
│  └─ More...                          │
│                                       │
│  [View More] [Export] [Share]        │
└───────────────────────────────────────┘
```

### Detailed Analytics Screen

```
┌───────────────────────────────────────┐
│       📊 Detailed Analytics           │
├─────────────────────────────────────┤
│                                       │
│  Period: [This Month ▼]              │
│                                       │
│  ┌─ SUMMARY ───────────────────────┐ │
│  │ Total Revenue:  90M₫            │ │
│  │ Transactions:   2,450           │ │
│  │ Avg Order:      36.7K₫          │ │
│  │ Repeat Rate:    32%             │ │
│  └─────────────────────────────────┘ │
│                                       │
│  ┌─ TOP ITEMS ──────────────────────┐ │
│  │ 1. Bún phở special   35% | 15.8M│ │
│  │ 2. Egg roll          28% | 12.6M│ │
│  │ 3. Spring roll       22% | 9.9M │ │
│  │ 4. Soup              15% | 6.7M │ │
│  └─────────────────────────────────┘ │
│                                       │
│  ┌─ TOP CUSTOMERS ──────────────────┐│
│  │ 1. Nguyễn Văn A    45 visits     │ │
│  │    └─ Total spent: 2.3M₫         │ │
│  │ 2. Trần Thị B      32 visits     │ │
│  │    └─ Total spent: 1.8M₫         │ │
│  └─────────────────────────────────┘ │
│                                       │
│  [Print Report] [Send Email] [Export]│
└───────────────────────────────────────┘
```

## 3.2 Customer Engagement Platform - UI Wireframe

### SMS Campaign Builder

```
┌───────────────────────────────────────┐
│    📬 Create SMS Campaign              │
├─────────────────────────────────────┤
│                                       │
│  Campaign Name:                      │
│  [Enter campaign name________]      │
│                                       │
│  Target Segment: [Choose ▼]          │
│  ├─ All customers (847)              │
│  ├─ Frequent buyers (250) *          │
│  ├─ First-time (120)                 │
│  ├─ Inactive 30 days (45)            │
│  └─ Custom filter...                 │
│                                       │
│  Message Template:                   │
│  ┌───────────────────────────────────┐│
│  │ Hi {name}! 🎉                      ││
│  │                                    ││
│  │ Come back to our shop today!      ││
│  │ Show code: COMEBACK20 for          ││
│  │ 20% off your next order ❤️        ││
│  │                                    ││
│  │ Valid today only!                  ││
│  │ Order now: [Link]                  ││
│  └───────────────────────────────────┘│
│  [120/160 characters]                │
│                                       │
│  Schedule:                           │
│  ○ Send now                          │
│  ◉ Schedule for: [2pm Today ▼]      │
│                                       │
│  Estimated Reach: 250 SMS            │
│  Cost: 125K₫ (at 500₫/SMS)          │
│                                       │
│  [Preview] [Save Draft] [Send SMS]   │
└───────────────────────────────────────┘
```

### Campaign Analytics Dashboard

```
┌───────────────────────────────────────┐
│    📊 Campaign Performance             │
├─────────────────────────────────────┤
│                                       │
│  Campaign: "Comeback20 Sale"         │
│  Sent: July 10 at 2:00 PM            │
│  Status: ✓ Completed                 │
│                                       │
│  ┌─ CORE METRICS ──────────────────┐ │
│  │ Sent:        250 SMS            │ │
│  │ Delivered:   248 (99.2%) ✓      │ │
│  │ Failed:      2 (0.8%)           │ │
│  │ Read Rate:   78 (31.4%)         │ │
│  │ Click Rate:  32 (12.9%)         │ │
│  │ Conversion:  8 orders (3.2%)    │ │
│  └─────────────────────────────────┘ │
│                                       │
│  ┌─ REVENUE IMPACT ────────────────┐ │
│  │ Total Orders: 8                 │ │
│  │ Order Value: 45K₫ avg           │ │
│  │ Revenue: 360K₫                  │ │
│  │ Cost: 125K₫                     │ │
│  │ ROI: 188% ✓ Great! 🎉          │ │
│  └─────────────────────────────────┘ │
│                                       │
│  ┌─ TIMELINE ──────────────────────┐ │
│  │ Sent:   14:00 ────────          │ │
│  │ Reads:  14:15 ──────────        │ │
│  │ Clicks: 14:20 ──────            │ │
│  │ Orders: 14:30 ─────             │ │
│  └─────────────────────────────────┘ │
│                                       │
│  [Create New Campaign] [Duplicate]   │
└───────────────────────────────────────┘
```

## 3.3 E-Invoice & Tax Compliance - UI Wireframe

### Invoice Archive

```
┌───────────────────────────────────────┐
│     📋 Invoice Archive                 │
├─────────────────────────────────────┤
│                                       │
│  Filter: [Month: July ▼] [Status ▼] │
│                                       │
│  ┌──────────────────────────────────┐│
│  │ Invoice #MOM-2025-07-0001        ││
│  │ Date: July 10, 14:23             ││
│  │ Amount: 100K₫ (VAT: 10K)        ││
│  │ Status: ✓ Submitted to Govt      ││
│  │ [View] [Download PDF] [Resend]   ││
│  └──────────────────────────────────┘│
│                                       │
│  ┌──────────────────────────────────┐│
│  │ Invoice #MOM-2025-07-0002        ││
│  │ Date: July 10, 14:45             ││
│  │ Amount: 250K₫ (VAT: 25K)        ││
│  │ Status: ✓ Submitted to Govt      ││
│  │ [View] [Download PDF] [Resend]   ││
│  └──────────────────────────────────┘│
│                                       │
│  ┌──────────────────────────────────┐│
│  │ Invoice #MOM-2025-07-0003        ││
│  │ Date: July 11, 09:12             ││
│  │ Amount: 180K₫ (VAT: 18K)        ││
│  │ Status: ✓ Submitted to Govt      ││
│  │ [View] [Download PDF] [Resend]   ││
│  └──────────────────────────────────┘│
│                                       │
│  Monthly Summary:                     │
│  Total Invoices: 2,450              │
│  Total Revenue: 90M₫                │
│  Total VAT: 9M₫                     │
│                                       │
│  [File Tax Return] [Print Report]    │
└───────────────────────────────────────┘
```

### Tax Filing Assistant

```
┌───────────────────────────────────────┐
│    💼 Tax Filing Assistant            │
├─────────────────────────────────────┤
│                                       │
│  📅 July 2025 Tax Summary             │
│                                       │
│  ✓ Step 1: Calculate Tax             │
│  ├─ Total Revenue: 90M₫              │
│  ├─ Invoices Generated: 2,450        │
│  ├─ VAT (10%): 9M₫                   │
│  ├─ Calculation: Automated ✓         │
│  └─ Status: Ready                    │
│                                       │
│  ✓ Step 2: Prepare Filing            │
│  ├─ Form Template: Loaded            │
│  ├─ Auto-fill: 90M₫ (Revenue)       │
│  ├─ Auto-fill: 9M₫ (Tax)             │
│  ├─ Status: Ready                    │
│  └─                                  │
│                                       │
│  ○ Step 3: Submit to Tax Authority   │
│  ├─ Destination: HCM Tax Office      │
│  ├─ Deadline: July 25, 2025          │
│  ├─ Days left: 5 days ⏰             │
│  └─ [Preview] [Submit Online]        │
│                                       │
│  💡 Tip: File before July 25 to      │
│  avoid penalties!                     │
│                                       │
│  [Chat Support] [Learn More]         │
└───────────────────────────────────────┘
```

---

---

# 4. DATA SCHEMA & UI MAPPING

## 4.1 Merchant Dashboard - Data Architecture

### Database Schema Design

```mermaid
graph TB
    subgraph "Raw Data Layer"
        QR_TXN["qr_transactions<br/>- txn_id<br/>- merchant_id<br/>- amount<br/>- timestamp<br/>- category<br/>- customer_phone"]
        CATEG["categories<br/>- category_id<br/>- category_name<br/>- tax_rate"]
    end

    subgraph "Analytics Layer"
        HOURLY["hourly_sales<br/>- merchant_id<br/>- hour<br/>- date<br/>- revenue<br/>- txn_count<br/>- category_breakdown"]
        DAILY["daily_sales<br/>- merchant_id<br/>- date<br/>- revenue<br/>- txn_count<br/>- repeat_rate<br/>- top_items"]
    end

    subgraph "Dashboard Materialized Views"
        DASHBOARD_HOME["dashboard_home_cache<br/>- merchant_id<br/>- today_revenue<br/>- yesterday_revenue<br/>- weekly_avg<br/>- monthly_target<br/>- cached_at"]
        CUSTOMER_INSIGHTS["customer_insights<br/>- merchant_id<br/>- repeat_count<br/>- top_customers<br/>- avg_order_value"]
    end

    QR_TXN --> HOURLY
    CATEG --> HOURLY
    HOURLY --> DAILY
    DAILY --> DASHBOARD_HOME
    QR_TXN --> CUSTOMER_INSIGHTS

    style QR_TXN fill:#2196F3,color:#fff
    style CATEG fill:#2196F3,color:#fff
    style HOURLY fill:#FFC107,color:#000
    style DAILY fill:#FFC107,color:#000
    style DASHBOARD_HOME fill:#4CAF50,color:#fff,stroke:#1B5E20,stroke-width:2px
    style CUSTOMER_INSIGHTS fill:#4CAF50,color:#fff,stroke:#1B5E20,stroke-width:2px
```

### Schema Definition

```sql
-- Raw transaction data
CREATE TABLE qr_transactions (
    txn_id VARCHAR(50) PRIMARY KEY,
    merchant_id VARCHAR(50) NOT NULL,
    amount BIGINT NOT NULL,  -- in VND
    timestamp TIMESTAMP NOT NULL,
    category_id VARCHAR(50),
    customer_phone VARCHAR(20),
    payment_method VARCHAR(20),
    status VARCHAR(20),  -- 'completed', 'pending', 'failed'
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    INDEX idx_merchant_timestamp (merchant_id, timestamp),
    INDEX idx_customer_phone (customer_phone)
);

-- Hourly aggregation (materialized view)
CREATE TABLE hourly_sales (
    merchant_id VARCHAR(50),
    date_hour TIMESTAMP NOT NULL,
    revenue BIGINT,
    transaction_count INT,
    category_breakdown JSON,  -- {"category_id": revenue}
    repeat_customer_count INT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (merchant_id, date_hour)
);

-- Daily dashboard cache
CREATE TABLE dashboard_daily_cache (
    merchant_id VARCHAR(50) PRIMARY KEY,
    date DATE NOT NULL,
    today_revenue BIGINT,
    yesterday_revenue BIGINT,
    week_avg_revenue BIGINT,
    monthly_target BIGINT,
    repeat_rate DECIMAL(5,2),  -- 0-100 %
    top_items JSON,  -- [{item: name, revenue: 1000000}]
    top_customers JSON,  -- [{phone: "0899xxx", spend: 500000}]
    cached_at TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### UI-to-DB Mapping

```mermaid
graph LR
    subgraph "Dashboard UI Component"
        UI["📊 Today Revenue Card<br/>Shows: 4.2M ₫<br/>vs Yesterday: +150K"]
    end

    subgraph "Data Sources"
        CACHE["Dashboard Cache<br/>today_revenue = 4,200,000<br/>yesterday_revenue = 4,050,000"]
        CALC["Calculated<br/>diff = 150,000"]
    end

    subgraph "SQL Query"
        QUERY["SELECT<br/>today_revenue,<br/>yesterday_revenue,<br/>FROM dashboard_daily_cache<br/>WHERE merchant_id = ?<br/>AND date = TODAY"]
    end

    UI -->|"fetches"| CACHE
    CACHE -->|"from"| QUERY
    QUERY -->|"reads"| DB["qr_transactions<br/>+ aggregation"]

    style UI fill:#FFC107,color:#000,stroke:#FFA000,stroke-width:2px
    style CACHE fill:#4CAF50,color:#fff
    style CALC fill:#4CAF50,color:#fff
    style QUERY fill:#2196F3,color:#fff
    style DB fill:#2196F3,color:#fff
```

---

## 4.2 Customer Engagement Platform - Data Schema

### Database Design

```mermaid
graph TB
    subgraph "Customer Master Data"
        CUST["customers<br/>- customer_id<br/>- merchant_id<br/>- phone<br/>- email<br/>- name (if collected)<br/>- created_at<br/>- last_purchase_date"]
        SEGMENT["customer_segments<br/>- segment_id<br/>- customer_id<br/>- segment_type<br/>- reason<br/>- created_at"]
    end

    subgraph "Purchase History"
        HISTORY["customer_purchases<br/>- purchase_id<br/>- customer_id<br/>- merchant_id<br/>- amount<br/>- date<br/>- items<br/>- payment_method"]
    end

    subgraph "Campaign Data"
        CAMPAIGN["sms_campaigns<br/>- campaign_id<br/>- merchant_id<br/>- name<br/>- target_segment<br/>- message<br/>- sent_at<br/>- status"]
        DELIVERY["campaign_delivery<br/>- delivery_id<br/>- campaign_id<br/>- customer_id<br/>- phone<br/>- status<br/>- delivered_at<br/>- read_at<br/>- clicked_at"]
    end

    subgraph "Analytics"
        ANALYTICS["campaign_analytics<br/>- campaign_id<br/>- sent_count<br/>- delivered_count<br/>- open_rate<br/>- click_rate<br/>- conversion_count<br/>- revenue_generated"]
    end

    HISTORY --> CUST
    CUST --> SEGMENT
    SEGMENT --> CAMPAIGN
    CAMPAIGN --> DELIVERY
    DELIVERY --> ANALYTICS

    style CUST fill:#2196F3,color:#fff,stroke:#0D47A1,stroke-width:2px
    style SEGMENT fill:#2196F3,color:#fff
    style HISTORY fill:#00BCD4,color:#000
    style CAMPAIGN fill:#4CAF50,color:#fff
    style DELIVERY fill:#4CAF50,color:#fff
    style ANALYTICS fill:#9C27B0,color:#fff
```

### Schema SQL

```sql
-- Customer master table
CREATE TABLE customers (
    customer_id VARCHAR(50) PRIMARY KEY,
    merchant_id VARCHAR(50) NOT NULL,
    phone VARCHAR(20) NOT NULL,
    email VARCHAR(100),
    customer_name VARCHAR(100),
    created_at TIMESTAMP,
    last_purchase_date DATE,
    total_purchases INT DEFAULT 0,
    total_spend BIGINT DEFAULT 0,
    frequency_score INT,  -- 0-100, how often they buy
    INDEX idx_merchant_phone (merchant_id, phone),
    INDEX idx_last_purchase (merchant_id, last_purchase_date)
);

-- Customer segments (e.g., "frequent_buyer", "at_risk", "vip")
CREATE TABLE customer_segments (
    segment_id VARCHAR(50) PRIMARY KEY,
    customer_id VARCHAR(50) NOT NULL,
    merchant_id VARCHAR(50),
    segment_type VARCHAR(50),  -- 'frequent', 'at_risk', 'vip', 'new'
    calculated_date DATE,
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
);

-- SMS campaign table
CREATE TABLE sms_campaigns (
    campaign_id VARCHAR(50) PRIMARY KEY,
    merchant_id VARCHAR(50) NOT NULL,
    campaign_name VARCHAR(200),
    message_template TEXT,
    target_segment VARCHAR(50),
    sent_at TIMESTAMP,
    scheduled_for TIMESTAMP,
    status VARCHAR(20),  -- 'draft', 'scheduled', 'sent', 'completed'
    created_at TIMESTAMP,
    updated_at TIMESTAMP,
    INDEX idx_merchant_status (merchant_id, status)
);

-- Campaign delivery log
CREATE TABLE campaign_delivery (
    delivery_id VARCHAR(50) PRIMARY KEY,
    campaign_id VARCHAR(50) NOT NULL,
    customer_id VARCHAR(50) NOT NULL,
    phone_number VARCHAR(20),
    message_text TEXT,
    status VARCHAR(20),  -- 'pending', 'sent', 'delivered', 'failed'
    sent_at TIMESTAMP,
    delivered_at TIMESTAMP,
    read_at TIMESTAMP,
    clicked_at TIMESTAMP,
    click_url VARCHAR(500),
    INDEX idx_campaign_customer (campaign_id, customer_id),
    FOREIGN KEY (campaign_id) REFERENCES sms_campaigns(campaign_id)
);

-- Campaign metrics (aggregated for fast analytics)
CREATE TABLE campaign_metrics (
    campaign_id VARCHAR(50) PRIMARY KEY,
    sent_count INT,
    delivered_count INT,
    failed_count INT,
    open_rate DECIMAL(5,2),  -- 0-100 %
    click_rate DECIMAL(5,2),
    conversion_count INT,
    revenue_generated BIGINT,
    cost_per_sms INT,  -- 500 VND typically
    roi_percent DECIMAL(6,2),
    updated_at TIMESTAMP
);
```

### UI Component to DB Mapping

```
┌─ SMS Campaign Builder UI ──────────┐
│ Target: [Frequent Buyers]          │
│ -> SELECT customers FROM customer_segments
│    WHERE segment_type = 'frequent'
│    AND merchant_id = '12345'
│    -> Returns: 250 customers
│
│ Message: "Hi {name}, come back..."
│ -> INSERT INTO sms_campaigns (...)
│    INSERT INTO campaign_delivery (...)
│    -> campaign_id = 'camp_001'
│
│ Cost: 250 SMS x 500₫ = 125K₫
│ -> Calculate from: SELECT COUNT(*) * 500
│    FROM customers WHERE segment_type = 'frequent'
└────────────────────────────────────┘

┌─ Campaign Analytics UI ────────────┐
│ Shows:                              │
│ - Sent: 250                         │
│ - Delivered: 248 (99.2%)            │
│ - Open: 78 (31.4%)                  │
│ - Click: 32 (12.9%)                 │
│ - ROI: 188%                         │
│ -> SELECT sent_count, delivered_count,
│           open_rate, click_rate, roi_percent
│    FROM campaign_metrics
│    WHERE campaign_id = 'camp_001'
└────────────────────────────────────┘
```

---

## 4.3 E-Invoice & Compliance - Data Schema

### Database Design

```mermaid
graph TB
    subgraph "Transaction Base"
        TXN["qr_transactions<br/>(reused from dashboard)"]
    end

    subgraph "Invoice Generation"
        INV["invoices<br/>- invoice_id<br/>- merchant_id<br/>- txn_id<br/>- amount<br/>- tax_amount<br/>- total<br/>- invoice_date<br/>- issue_date<br/>- status"]
    end

    subgraph "Tax Calculation"
        TAX["invoice_tax_detail<br/>- invoice_id<br/>- category<br/>- revenue<br/>- tax_rate<br/>- tax_amount"]
    end

    subgraph "Government Submission"
        GOV["govt_submission_log<br/>- submission_id<br/>- merchant_id<br/>- month<br/>- total_revenue<br/>- total_tax<br/>- submitted_at<br/>- response_status<br/>- reference_no"]
    end

    TXN --> INV
    INV --> TAX
    TAX --> GOV

    style TXN fill:#2196F3,color:#fff
    style INV fill:#FF1744,color:#fff,stroke:#C00,stroke-width:2px
    style TAX fill:#FFC107,color:#000
    style GOV fill:#4CAF50,color:#fff
```

### Schema SQL

```sql
-- Invoice table
CREATE TABLE invoices (
    invoice_id VARCHAR(50) PRIMARY KEY,
    merchant_id VARCHAR(50) NOT NULL,
    txn_id VARCHAR(50) NOT NULL,
    invoice_number VARCHAR(20),  -- MOM-2025-07-0001
    invoice_date DATE NOT NULL,
    issue_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    total_amount BIGINT NOT NULL,  -- in VND
    tax_amount BIGINT,
    tax_rate DECIMAL(5,2),
    total_with_tax BIGINT,
    customer_phone VARCHAR(20),
    customer_name VARCHAR(100),
    status VARCHAR(20),  -- 'draft', 'issued', 'submitted', 'acknowledged'
    submitted_to_govt TIMESTAMP,
    govt_reference_no VARCHAR(50),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    INDEX idx_merchant_month (merchant_id, invoice_date)
);

-- Tax detail per invoice
CREATE TABLE invoice_tax_details (
    detail_id VARCHAR(50) PRIMARY KEY,
    invoice_id VARCHAR(50) NOT NULL,
    category_id VARCHAR(50),
    revenue BIGINT,
    tax_rate DECIMAL(5,2),  -- e.g., 10.0 for 10%
    tax_amount BIGINT,
    FOREIGN KEY (invoice_id) REFERENCES invoices(invoice_id)
);

-- Monthly tax summary for filing
CREATE TABLE tax_monthly_summary (
    summary_id VARCHAR(50) PRIMARY KEY,
    merchant_id VARCHAR(50) NOT NULL,
    year INT,
    month INT,
    total_revenue BIGINT,
    total_tax BIGINT,
    invoice_count INT,
    status VARCHAR(20),  -- 'calculated', 'filed', 'acknowledged'
    filed_at TIMESTAMP,
    govt_response TIMESTAMP,
    filing_reference_no VARCHAR(50),
    created_at TIMESTAMP,
    updated_at TIMESTAMP,
    UNIQUE KEY (merchant_id, year, month)
);

-- Government submission log
CREATE TABLE govt_submission_log (
    submission_id VARCHAR(50) PRIMARY KEY,
    merchant_id VARCHAR(50) NOT NULL,
    month INT,
    year INT,
    total_invoices INT,
    total_revenue BIGINT,
    total_tax BIGINT,
    submitted_at TIMESTAMP,
    response_status VARCHAR(20),  -- 'pending', 'accepted', 'rejected'
    response_message TEXT,
    govt_reference_no VARCHAR(100),
    created_at TIMESTAMP
);
```

### Sample Data Mapping: Invoice Generation

```sql
-- When merchant receives QR payment
INSERT INTO qr_transactions VALUES (
    'txn_12345',
    'merchant_789',
    100000,  -- 100K VND
    '2025-07-10 14:23:45',
    'category_food',
    '0899123456',
    'qr_dynamic',
    'completed'
);

-- Auto-generate invoice (backend process < 5 sec)
INSERT INTO invoices VALUES (
    'inv_001',
    'merchant_789',
    'txn_12345',
    'MOM-2025-07-0001',
    '2025-07-10',
    CURRENT_TIMESTAMP,
    100000,
    10000,  -- 10% tax
    10.0,
    110000,
    '0899123456',
    'Nguyễn Văn A',  -- if captured
    'issued',
    CURRENT_TIMESTAMP,
    'MOMO-EVT-2025-07-0001'
);

-- Insert tax detail
INSERT INTO invoice_tax_details VALUES (
    'tax_001',
    'inv_001',
    'category_food',
    100000,
    10.0,
    10000
);

-- Update monthly summary
UPDATE tax_monthly_summary SET
    total_revenue = total_revenue + 100000,
    total_tax = total_tax + 10000,
    invoice_count = invoice_count + 1,
    updated_at = CURRENT_TIMESTAMP
WHERE merchant_id = 'merchant_789'
  AND year = 2025
  AND month = 7;
```

---

## 4.4 Complete User Journey Data Flow

```mermaid
graph TB
    subgraph "1. Customer Payment"
        A["👤 Customer pays<br/>100K at QR"]
        A -->|"triggers"| B["🔌 QR Event<br/>txn_id, amount,<br/>timestamp, category"]
    end

    subgraph "2. Data Ingestion"
        B -->|"streamed to"| C["📥 Real-time Pipeline<br/>Kafka/Kinesis"]
        C -->|"1 min later"| D["💾 Raw DB<br/>qr_transactions"]
    end

    subgraph "3. Analytics Processing"
        D -->|"hourly agg"| E["⏰ Hourly Sales<br/>hourly_sales table"]
        D -->|"daily agg"| F["📅 Daily Cache<br/>dashboard_daily_cache"]
    end

    subgraph "4. Dashboard Display"
        F -->|"API call<br/>< 100ms"| G["🏪 Dashboard<br/>Shows 4.2M revenue"]
    end

    subgraph "5. Invoice Generation"
        D -->|"< 5 sec"| H["📋 Auto Invoice<br/>invoices table"]
        H -->|"submit"| I["🏛️ Govt eInvoice<br/>Portal"]
    end

    subgraph "6. Customer Engagement"
        D -->|"extract phone"| J["📱 Customer DB<br/>customers table"]
        J -->|"segment"| K["🎯 Segments<br/>frequent_buyer"]
        K -->|"campaign"| L["📬 SMS Send<br/>delivery log"]
        L -->|"track"| M["📊 Analytics<br/>campaign_metrics"]
    end

    style A fill:#FFC107,color:#000
    style B fill:#FF9800,color:#fff
    style C fill:#2196F3,color:#fff
    style D fill:#2196F3,color:#fff
    style E fill:#00BCD4,color:#000
    style F fill:#4CAF50,color:#fff
    style G fill:#4CAF50,color:#fff,stroke:#1B5E20,stroke-width:2px
    style H fill:#FF1744,color:#fff
    style I fill:#FF1744,color:#fff
    style J fill:#9C27B0,color:#fff
    style K fill:#9C27B0,color:#fff
    style L fill:#9C27B0,color:#fff
    style M fill:#9C27B0,color:#fff
```

---

## 4.5 API Contracts (Product Team View)

### Dashboard API

```json
{
  "endpoint": "GET /v1/merchant/dashboard/home",
  "description": "Get today's dashboard summary",
  "request": {
    "merchant_id": "string (required)",
    "date": "YYYY-MM-DD (optional, default today)"
  },
  "response": {
    "today_revenue": 4200000,
    "yesterday_revenue": 4050000,
    "weekly_avg": 4100000,
    "monthly_target": 5000000,
    "target_progress_percent": 84,
    "repeat_rate": 35,
    "top_items": [
      {"name": "Bún phở", "revenue": 1800000, "percent": 43},
      {"name": "Egg roll", "revenue": 900000, "percent": 21}
    ],
    "top_customers": [
      {"phone": "0899123456", "name": "Nguyễn A", "purchases": 45, "total_spend": 2300000}
    ],
    "cached_at": "2025-07-14T14:00:00Z"
  }
}
```

### SMS Campaign API

```json
{
  "endpoint": "POST /v1/merchant/campaigns/sms/send",
  "description": "Send SMS campaign to customer segment",
  "request": {
    "merchant_id": "string",
    "campaign_name": "Comeback20 Sale",
    "segment_type": "frequent_buyers",
    "message_template": "Hi {name}, come back for 20% off!",
    "scheduled_for": "2025-07-14T14:00:00Z"
  },
  "response": {
    "campaign_id": "camp_12345",
    "target_count": 250,
    "status": "scheduled",
    "cost_vnd": 125000,
    "scheduled_at": "2025-07-14T14:00:00Z"
  }
}
```

### Invoice Generation API

```json
{
  "endpoint": "POST /v1/merchant/invoices/generate",
  "description": "Auto-generate invoice from QR transaction (internal)",
  "request": {
    "txn_id": "txn_12345",
    "merchant_id": "merchant_789",
    "amount": 100000
  },
  "response": {
    "invoice_id": "inv_001",
    "invoice_number": "MOM-2025-07-0001",
    "status": "issued",
    "submitted_to_govt": true,
    "govt_reference": "MOMO-EVT-2025-07-0001"
  }
}
```

---

## 4.6 Figma Component Library Map

```mermaid
graph TB
    subgraph "Dashboard Components"
        C1["KPI Card<br/>Revenue/Target<br/>Comparison metric"]
        C2["Line Chart<br/>7-day trend<br/>Interactive"]
        C3["Category Grid<br/>Item breakdown<br/>Top performers"]
        C4["Customer List<br/>Top buyers<br/>Phone/spend"]
    end

    subgraph "Campaign Components"
        C5["Segment Selector<br/>Dropdown<br/>Count display"]
        C6["Message Editor<br/>Text input<br/>Char counter"]
        C7["Schedule Picker<br/>Date + Time<br/>TZ aware"]
        C8["Cost Calculator<br/>Real-time<br/>ROI projection"]
    end

    subgraph "Invoice Components"
        C9["Invoice Card<br/>Display<br/>Status badge"]
        C10["Tax Summary<br/>Breakdown<br/>Calculation"]
        C11["Filing Wizard<br/>Step indicator<br/>Form fields"]
    end

    subgraph "Shared Components"
        SHARED["Modal, Button,<br/>Input, Dropdown,<br/>Table, Toast"]
    end

    C1 --> SHARED
    C2 --> SHARED
    C3 --> SHARED
    C4 --> SHARED
    C5 --> SHARED
    C6 --> SHARED
    C7 --> SHARED
    C8 --> SHARED
    C9 --> SHARED
    C10 --> SHARED
    C11 --> SHARED

    style C1 fill:#2196F3,color:#fff
    style C2 fill:#2196F3,color:#fff
    style C3 fill:#2196F3,color:#fff
    style C4 fill:#2196F3,color:#fff
    style C5 fill:#4CAF50,color:#fff
    style C6 fill:#4CAF50,color:#fff
    style C7 fill:#4CAF50,color:#fff
    style C8 fill:#4CAF50,color:#fff
    style C9 fill:#FF1744,color:#fff
    style C10 fill:#FF1744,color:#fff
    style C11 fill:#FF1744,color:#fff
    style SHARED fill:#9C27B0,color:#fff,stroke:#6A1B9A,stroke-width:2px
```

---

# APPENDIX: Implementation Roadmap

```mermaid
timeline
    title SME Solutions Product Roadmap 2025-2026
    
    section Q2 2025
        🚀 Dashboard MVP Launch
        : Daily sales by hour/category
        : Top items & customers
        : Target tracking
        : 1K merchants beta
    
    section Q3 2025
        📱 Customer Engagement
        : SMS campaign builder
        : Customer segmentation
        : Campaign analytics
        : Scale to 50K merchants
    
    section Q4 2025
        📋 Compliance Suite
        : Auto e-invoicing
        : Tax calculation
        : Govt submission
        : 200K merchants
    
    section Q1 2026
        💰 Merchant Financing
        : Quick loans
        : Credit decisioning
        : AI underwriting
        : Target: $10M loan book
```

---

**Document Version**: 1.0  
**Last Updated**: July 14, 2026  
**Owner**: Product Manager - SME Merchants  
**Status**: Ready for Engineering Kickoff

