# 💳 Payment & Transfer Services

## Overview

Payment & Transfer is MoMo's core money movement engine, enabling millions of users to transfer funds instantly, safely, and conveniently.

---

## Product Architecture

```mermaid
graph TB
    subgraph "User Touchpoints"
        A["📱 MoMo App"]
        B["🤖 Moni Bot"]
        C["🏪 Merchant POS"]
    end

    subgraph "Payment Products"
        P1["💳 E-Wallet<br/>- Balance Management<br/>- Multi-currency<br/>- Settlement"]
        P2["⏰ PayLater<br/>- Credit Limit<br/>- Installments<br/>- Smart Repayment"]
        P3["🔄 Transfers<br/>- P2P Transfer<br/>- Bulk Payroll<br/>- Scheduled Transfer"]
        P4["🏧 Cash Flow<br/>- ATM Withdrawal<br/>- Deposit ATM<br/>- Bank Link"]
    end

    subgraph "Infrastructure"
        I1["💾 Wallet Engine<br/>- Real-time Balance<br/>- Transaction Log<br/>- Settlement"]
        I2["🔐 Risk & Fraud<br/>- Risk Scoring<br/>- Fraud Detection<br/>- Rate Limiting"]
        I3["🌐 Gateway<br/>- Bank Integration<br/>- Gateway API<br/>- Reconciliation"]
    end

    A -->|"Transfer"| P3
    A -->|"Payment"| P1
    B -->|"Bill Pay"| P3
    C -->|"QR Payment"| P1
    
    P1 --> I1
    P2 --> I1
    P3 --> I1
    P4 --> I3
    
    I1 --> I2
    I3 --> I2

    style A fill:#FF1744,color:#fff
    style B fill:#FF1744,color:#fff
    style C fill:#FF1744,color:#fff
    style P1 fill:#00BCD4,color:#000
    style P2 fill:#00BCD4,color:#000
    style P3 fill:#00BCD4,color:#000
    style P4 fill:#00BCD4,color:#000
    style I1 fill:#4CAF50,color:#fff
    style I2 fill:#2196F3,color:#fff
    style I3 fill:#FF9800,color:#fff
```

---

## Payment Flow Diagram

```mermaid
sequenceDiagram
    participant User
    participant App
    participant PaymentEngine
    participant Bank
    participant Receiver

    User ->> App: Initiate Transfer
    App ->> PaymentEngine: Validate Transaction
    PaymentEngine ->> PaymentEngine: Risk Check & Auth
    PaymentEngine ->> Bank: Debit Request
    Bank -->> PaymentEngine: Confirmed
    PaymentEngine ->> PaymentEngine: Record Transaction
    PaymentEngine ->> Receiver: Credit Notification
    PaymentEngine ->> App: Success Confirmation
    App -->> User: Transaction Complete ✓

    Note over PaymentEngine: Real-time Processing<br/>99.9% Success Rate
```

---

## Core Products

### 1. **E-Wallet (Ví MoMo)**
- Real-time balance management
- Multi-currency support
- Instant peer-to-peer transfers
- **Daily Limit**: 500M₫ | **Monthly Limit**: 2B₫

### 2. **PayLater (Ví Trả Sau)**
- 0% interest payment later
- Flexible installments (3-12 months)
- Automatic reminder system
- Credit limit: 10M-100M₫

### 3. **Transfer Services**
- **Instant**: To MoMo users (< 5 sec)
- **Scheduled**: Future-dated transfers
- **Bulk**: Payroll & batch payments
- **International**: Regional remittance

### 4. **Cash Flow Management**
- Deposit ATMs across Vietnam
- Contactless ATM withdrawal
- Bank account linking
- Open banking integration

---

## Payment Methods Integration

```mermaid
graph TB
    subgraph "Funding Sources"
        A["🏧 Bank Account"]
        B["💰 Cash (ATM/Branch)"]
        C["💳 Debit Card"]
        D["⚡ Direct Pay"]
    end

    subgraph "MoMo Wallet"
        W["💳 MoMo Balance"]
    end

    subgraph "Payment Destinations"
        P1["👤 Friend/Family"]
        P2["🏪 Merchant"]
        P3["🏛️ Bill Provider"]
        P4["🏦 Bank Account"]
    end

    A -->|"Link & Top-up"| W
    B -->|"Deposit"| W
    C -->|"Direct Pay"| W
    D -->|"Digital Payment"| W

    W -->|"Send"| P1
    W -->|"Pay"| P2
    W -->|"Bills"| P3
    W -->|"Withdraw"| P4

    style A fill:#FF9800,color:#fff
    style B fill:#FF9800,color:#fff
    style C fill:#FF9800,color:#fff
    style D fill:#FF9800,color:#fff
    style W fill:#FF1744,color:#fff,stroke:#C00,stroke-width:3px
    style P1 fill:#00BCD4,color:#000
    style P2 fill:#00BCD4,color:#000
    style P3 fill:#00BCD4,color:#000
    style P4 fill:#00BCD4,color:#000
```

---

## Key Metrics Dashboard

| Metric | 2024 Target | 2025 Target | Calculation |
|--------|------------|-----------|------------|
| Payment Success Rate | 99.8% | 99.95% | Successful Txn / Total Attempts |
| Avg Txn Settlement | < 100ms | < 50ms | P99 latency |
| Payment Volume (GMV) | $5B | $8B | Total transaction value |
| Daily Active Payers | 4M | 6M | Users making 1+ payment/day |
| Fraud Rate | < 0.01% | < 0.005% | Disputed txn / Total txn |
| PayLater Penetration | 15% | 25% | PayLater users / Total users |

---

## User Experience Optimization

```mermaid
graph LR
    A["👤 User Opens App"] -->|"< 200ms"| B["⏱️ Wallet Loads<br/>Real-time Balance"]
    B -->|"UI Ready"| C["🎯 Payment Options"]
    C -->|"Tap Transfer"| D["📝 Quick Entry<br/>Phone Number"]
    D -->|"< 1 sec"| E["✅ Confirm<br/>Bio/Face ID"]
    E -->|"< 5 sec"| F["✨ Success<br/>Notification"]

    style A fill:#FFC107,color:#000
    style B fill:#FFC107,color:#000
    style C fill:#00BCD4,color:#000
    style D fill:#00BCD4,color:#000
    style E fill:#4CAF50,color:#fff
    style F fill:#4CAF50,color:#fff
```

---

## Strategic Initiatives 2025-2026

1. **Open Banking Integration**
   - Direct bank account linking
   - Multi-bank balance view
   - Unified payment experience

2. **Cross-Border Payments**
   - Regional remittance (Cambodia, Laos)
   - International transfers
   - Crypto gateway integration

3. **Merchant Ecosystem**
   - QR Payment ubiquity
   - Offline payment capability
   - Merchant settlement acceleration

4. **PayLater Scale**
   - Credit limit increase
   - Installment options expansion
   - Merchant adoption (F&B, Retail)

---

## Competitive Positioning

| Feature | MoMo | Bank Apps | Fintech Competitors |
|---------|------|-----------|-------------------|
| Instant Transfer | ✅ | 1-2 hours | ✅ |
| PayLater 0% | ✅ | Limited | ✅ |
| Merchant Coverage | ✅ | Basic | Basic |
| AI Features | ✅ | None | Limited |
| Accessibility | ✅ | Basic | Basic |

---

## Related Documentation

- [Business Solutions - Merchant Payments](./business-solutions.md)
- [Security & Compliance](./security-compliance.md)
- [Growth & Discovery Platform](./growth-discovery.md)

---

**Last Updated**: July 2026 | **Owner**: Head of Product, Payment & Transfer
