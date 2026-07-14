# 🔍 Growth & Discovery Platform

## Overview

MoMo's Growth & Discovery Platform is the intelligent engine that helps 30M+ users discover the right financial services at the right time through AI-powered personalization and seamless UX.

---

## Discovery Platform Architecture

```mermaid
graph TB
    subgraph "User Entry Points"
        H["🏠 Homescreen<br/>- Service Grid<br/>- Recommendations<br/>- Trending"]
        S["🔍 Search<br/>- Voice Search<br/>- Category Browse<br/>- Smart Suggestions"]
        T["🔔 Notifications<br/>- Smart Push<br/>- Contextual Offers<br/>- Personal Alerts"]
    end

    subgraph "AI/ML Engine"
        R["🤖 Recommendation Engine<br/>- Content-based<br/>- Collaborative<br/>- Graph-based"]
        P["📊 Personalization<br/>- User Segments<br/>- Behavior Patterns<br/>- Intent Detection"]
        A["🧠 AutoXsell<br/>- LLM-powered<br/>- Cross-sell logic<br/>- Hyperpersonalization"]
    end

    subgraph "Content Layer"
        SV["📱 Service Catalog<br/>100+ Services<br/>1M+ Merchants"]
        ADS["🎯 Campaigns<br/>Promotions<br/>Offers<br/>Marketing"]
        RANK["📈 Ranking<br/>Service Score<br/>Relevance<br/>Performance"]
    end

    subgraph "Data Foundation"
        UV["🔗 User Vector<br/>Behavior<br/>Preferences<br/>Context"]
        EVENTS["📊 Event Tracking<br/>Real-time<br/>Behavioral<br/>Transactional"]
    end

    H --> R
    S --> R
    T --> R
    
    R --> A
    P --> A
    
    A --> SV
    A --> ADS
    A --> RANK
    
    SV --> UV
    ADS --> UV
    EVENTS --> UV
    EVENTS --> P

    style H fill:#FFC107,color:#000
    style S fill:#FFC107,color:#000
    style T fill:#FFC107,color:#000
    style R fill:#2196F3,color:#fff
    style P fill:#2196F3,color:#fff
    style A fill:#FF1744,color:#fff,stroke:#C00,stroke-width:2px
    style SV fill:#4CAF50,color:#fff
    style ADS fill:#4CAF50,color:#fff
    style RANK fill:#4CAF50,color:#fff
    style UV fill:#9C27B0,color:#fff
    style EVENTS fill:#9C27B0,color:#fff
```

---

## Homescreen Experience

### Current State
```mermaid
graph TB
    subgraph "Homescreen Zones"
        Z1["🎯 Top Zone<br/>Personalized Banner<br/>High-intent offer<br/>AI-selected"]
        Z2["📊 Service Grid<br/>8-12 Services<br/>Ranked by relevance<br/>User preference"]
        Z3["🎁 Promo Zone<br/>Active campaigns<br/>Time-sensitive<br/>Category mix"]
        Z4["📈 Trending<br/>Popular services<br/>Community activity<br/>Dynamic"]
    end

    Z1 -->|"40% Click-through"| A["✨ Conversion"]
    Z2 -->|"25% Discovery"| A
    Z3 -->|"20% Engagement"| A
    Z4 -->|"15% Exploration"| A

    style Z1 fill:#FF1744,color:#fff
    style Z2 fill:#2196F3,color:#fff
    style Z3 fill:#FFC107,color:#000
    style Z4 fill:#4CAF50,color:#fff
    style A fill:#9C27B0,color:#fff,stroke:#6A1B9A,stroke-width:2px
```

### 2025 Improvements
- Expanded personalization coverage
- Video preview support
- Subscription service promotion
- AI agent recommendations

---

## Search & Service Discovery

```mermaid
graph LR
    A["👤 User Opens Search<br/>or taps category"] -->|"Instant results"| B["🔍 Smart Search<br/>- Voice + Text<br/>- Fuzzy matching<br/>- Intent detection"]
    B -->|"< 200ms"| C["📱 Results Page<br/>- Services ranked<br/>- Merchants filtered<br/>- Promo highlighted"]
    C -->|"Tap service"| D["📊 Service Detail<br/>- Description<br/>- Reviews<br/>- Price"]
    D -->|"CTA Click"| E["✅ Action<br/>- Use service<br/>- Install<br/>- Learn more"]

    style A fill:#FFC107,color:#000
    style B fill:#2196F3,color:#fff
    style C fill:#2196F3,color:#fff
    style D fill:#00BCD4,color:#000
    style E fill:#4CAF50,color:#fff
```

---

## AI Personalization Engines

### 🤖 AutoXsell - Hyperpersonalization

**What**: LLM-powered engine that understands user context and recommends services naturally

**How it works**:
```mermaid
sequenceDiagram
    participant User
    participant Context
    participant LLM
    participant Recommender
    participant Display

    User ->> Context: User opens app
    Context ->> LLM: Current context + history
    LLM ->> LLM: Understand intent
    LLM ->> Recommender: Best 3-5 services
    Recommender ->> Display: Personalized ranking
    Display ->> User: Tailored homescreen

    Note over LLM: Considers:<br/>- Time of day<br/>- Recent behavior<br/>- Purchase history<br/>- Similar users
```

**Results (2024-2026)**:
- 30% increase in service discovery traffic
- 55% increase in daily financial service registrations
- 10% reduction in single-use users

### 📊 Recommendation Engine

**Components**:
- **Content-based**: Similar services based on attributes
- **Collaborative Filtering**: Users like me also used X
- **Graph-based**: Relationship networks between services
- **Contextual**: Time, location, device, behavior

---

## Growth Loops

```mermaid
graph TB
    subgraph "Acquisition Loop"
        A1["👤 New User"] -->|"Onboarding"| A2["📱 First Service<br/>(Payment)"]
        A2 -->|"Success"| A3["🎁 Referral Bonus<br/>Invite Friends"]
        A3 -->|"Shared Link"| A4["👥 New Users<br/>via Referral"]
        A4 -->|"Loop"| A2
    end

    subgraph "Engagement Loop"
        E1["💳 Payment Service"] -->|"Success"| E2["🔍 Discovery<br/>Next Service"]
        E2 -->|"Cross-sell"| E3["💰 Finance Service<br/>(Invest/Loan)"]
        E3 -->|"Engagement"| E4["📊 Dashboard<br/>View Holdings"]
        E4 -->|"Habit"| E1
    end

    subgraph "Retention Loop"
        R1["📊 Regular Usage"] -->|"Points"| R2["🎁 MoMo Xu<br/>Rewards"]
        R2 -->|"Redeem"| R3["🛍️ Use Reward<br/>(Cashback/Voucher)"]
        R3 -->|"Habit"| R1
    end

    style A1 fill:#FFC107,color:#000
    style A2 fill:#FF1744,color:#fff
    style A3 fill:#FFC107,color:#000
    style A4 fill:#FF1744,color:#fff

    style E1 fill:#FF1744,color:#fff
    style E2 fill:#2196F3,color:#fff
    style E3 fill:#4CAF50,color:#fff
    style E4 fill:#9C27B0,color:#fff

    style R1 fill:#FF1744,color:#fff
    style R2 fill:#9C27B0,color:#fff
    style R3 fill:#FFC107,color:#000
```

---

## MoMo Xu Loyalty Program

### Program Structure

```mermaid
graph TB
    subgraph "Earn Xu"
        E1["💳 Every Payment<br/>1 Xu per 1,000₫"]
        E2["🎁 Special Offers<br/>Bonus Xu<br/>2-10x multiplier"]
        E3["📱 Daily Activities<br/>Check-in bonus<br/>Milestone rewards"]
        E4["🎯 Campaign Rewards<br/>Referral bonus<br/>Task completion"]
    end

    subgraph "Redeem Xu"
        R1["💰 Cashback<br/>Direct wallet<br/>500 Xu = 10K₫"]
        R2["🛍️ Vouchers<br/>Partner stores<br/>Discount codes"]
        R3["🎮 Games<br/>Play for prizes<br/>Spin & Win"]
        R4["📊 Premium<br/>Unlock features<br/>Priority support"]
    end

    E1 --> R1
    E2 --> R1
    E3 --> R2
    E4 --> R3

    style E1 fill:#FFC107,color:#000
    style E2 fill:#FFC107,color:#000
    style E3 fill:#FFC107,color:#000
    style E4 fill:#FFC107,color:#000
    style R1 fill:#9C27B0,color:#fff
    style R2 fill:#9C27B0,color:#fff
    style R3 fill:#9C27B0,color:#fff
    style R4 fill:#9C27B0,color:#fff
```

---

## Metrics & Analytics

### Discovery Platform KPIs

| Metric | 2024 | 2025 Target | Definition |
|--------|------|------------|-----------|
| Homescreen CTR | 35% | 45% | Clicks / Impressions |
| Service Discovery Rate | 45% | 60% | Users discovering 1+ new service/month |
| Cross-sell Rate | 30% | 45% | Users using 3+ service categories |
| Daily Service Usage | 2.1 | 2.8 | Avg services used per DAU |
| Personalization Accuracy | 72% | 82% | Relevant recommendation rate |
| MoMo Xu Participation | 55% | 75% | Active users in loyalty program |
| Referral Conversion | 18% | 28% | Signups from referral links |

---

## Growth vs Discovery Balance

```mermaid
graph TB
    subgraph "Growth Metrics"
        G1["📈 DAU Growth<br/>3% MoM"]
        G2["👥 New Signups<br/>2.5M/month"]
        G3["🔄 Retention<br/>D30: 45%"]
    end

    subgraph "Discovery Metrics"
        D1["🔍 Service Adoption<br/>New services: 25%/month"]
        D2["💰 ARPU Growth<br/>+15% YoY"]
        D3["📊 Engagement<br/>Sessions: 3.5/week"]
    end

    subgraph "Balance"
        B["⚖️ Growth x Discovery<br/>= Sustainable Scale"]
    end

    G1 --> B
    G2 --> B
    G3 --> B
    D1 --> B
    D2 --> B
    D3 --> B

    style G1 fill:#FF1744,color:#fff
    style G2 fill:#FF1744,color:#fff
    style G3 fill:#FF1744,color:#fff
    style D1 fill:#2196F3,color:#fff
    style D2 fill:#2196F3,color:#fff
    style D3 fill:#2196F3,color:#fff
    style B fill:#9C27B0,color:#fff,stroke:#6A1B9A,stroke-width:3px
```

---

## 2025-2026 Strategic Initiatives

### Q1-Q2 2025: Agentic Search
- Graph-based service discovery
- Natural language understanding
- Multi-step recommendation
- Expected: 25% improvement in discovery

### Q3-Q4 2025: AI Video Preview
- Auto-generated service videos
- Micro-interactions
- Contextual demos
- Expected: 30% CTR improvement

### 2026: Predictive Discovery
- Predict user needs before action
- Proactive service suggestions
- Seasonal/contextual awareness
- Expected: 40% increase in service adoption

---

## Competitive Positioning

```mermaid
graph TB
    subgraph "MoMo Strengths"
        A["✅ LLM-powered personalization"]
        B["✅ Largest service catalog (100+)"]
        C["✅ Real-time user behavior data"]
        D["✅ AI/ML infrastructure maturity"]
    end

    subgraph "Market Position"
        M["🥇 #1 in AI-Powered Discovery<br/>in Southeast Asia"]
    end

    A --> M
    B --> M
    C --> M
    D --> M

    style A fill:#4CAF50,color:#fff
    style B fill:#4CAF50,color:#fff
    style C fill:#4CAF50,color:#fff
    style D fill:#4CAF50,color:#fff
    style M fill:#FF1744,color:#fff,stroke:#C00,stroke-width:3px
```

---

## Related Documentation

- [Payment Services](./payments.md)
- [Financial Services](./financial-services.md)
- [Business Solutions](./business-solutions.md)
- [Security & Compliance](./security-compliance.md)

---

**Last Updated**: July 2026 | **Owner**: Head of Growth Platform Product
