# Thiết kế sản phẩm SME Merchants – MoMo

## 1. Yêu cầu nghiệp vụ

### 1.1 Vấn đề cần giải quyết
Các merchant SME thường gặp ba rào cản chính: thiếu dữ liệu bán hàng theo thời gian thực, khó tiếp cận khách hàng mới và phải xử lý thủ công các công việc thuế, hóa đơn và chăm sóc khách hàng. MoMo cần cung cấp một bộ giải pháp giúp merchant tăng doanh thu, tối ưu chi phí marketing và giảm thao tác vận hành.

### 1.2 Đối tượng sử dụng chính
- Cửa hàng nhỏ / quán ăn / tiệm tiện lợi
- Chủ shop bán lẻ có ít nhân sự
- Merchant đang muốn mở rộng khách hàng mới và tăng tần suất mua hàng

### 1.3 Mục tiêu sản phẩm
- Tăng doanh thu trung bình trên mỗi merchant
- Giảm thời gian kiểm tra bán hàng và theo dõi hiệu quả
- Tự động tạo hóa đơn điện tử và nộp thuế đúng quy định
- Tối ưu chi phí marketing bằng Facebook Ads và Google Ads thay vì chỉ phụ thuộc vào SMS

### 1.4 KPI trọng tâm
| KPI | Target |
|---|---:|
| Daily revenue | +15% in 90 days |
| Repeat rate | +10% |
| Customer acquisition cost | -20% |
| Invoice automation rate | 90% |
| Active merchant rate | 80% in 30 days |

```mermaid
flowchart LR
    A[Merchant SME] --> B[Dashboard bán hàng]
    A --> C[Marketing Growth]
    A --> D[Hóa đơn & Thuế]
    B --> E[Doanh thu + phân tích]
    C --> F[Facebook Ads + Google Ads]
    D --> G[Nộp hồ sơ điện tử]
```

---

## 2. Thiết kế sản phẩm

### 2.1 Bộ sản phẩm cốt lõi

#### A. Merchant Dashboard
- Tổng quan doanh thu hôm nay, tuần, tháng
- Phân tích theo giờ, nhóm hàng và khách hàng
- Cảnh báo mục tiêu chưa đạt

#### B. Growth Marketing Suite
- Launch ad campaigns on Facebook Ads and Google Ads
- Track ROI, CPA, conversion rate, and repeat rate
- Target customers by geography, category, and purchase behavior

#### C. E-Invoice & Compliance
- Tự động sinh hóa đơn từ giao dịch QR
- Tính thuế và chuẩn bị hồ sơ nộp cho cơ quan thuế
- Ghi nhận trạng thái nộp và mã tham chiếu

### 2.2 Luồng hoạt động

```mermaid
sequenceDiagram
    participant C as Customer
    participant M as Merchant
    participant P as MoMo Platform
    participant A as Ads Engine
    participant I as Invoice Engine

    C->>M: Thanh toán bằng QR
    M->>P: Gửi giao dịch
    P->>P: Tổng hợp dữ liệu bán hàng
    P->>A: Cập nhật dữ liệu để tối ưu quảng cáo
    A-->>M: Báo cáo hiệu quả Facebook/Google Ads
    P->>I: Tạo hóa đơn điện tử
    I-->>M: Gửi hóa đơn + trạng thái nộp thuế
```

### 2.3 Kiến trúc hệ thống

```mermaid
graph TB
    UI[Merchant App/Web] --> API[API Gateway]
    API --> DASH[Dashboard Service]
    API --> ADS[Ads Campaign Service]
    API --> INV[Invoice Service]
    DASH --> DB[(Data Store)]
    ADS --> DB
    INV --> DB
    DB --> ANALYTICS[Analytics Layer]
```

---

## 3. Wireframe UI cần thiết

### 3.1 Dashboard tổng quan merchant

```text
+-----------------------------------------------------------+
| MoMo Merchant Center                 [Báo cáo] [Cài đặt] |
|-----------------------------------------------------------|
| Tổng doanh thu hôm nay: 4.2M ₫   | Mục tiêu tháng: 5M ₫ |
| Tăng so với hôm qua: +150K ₫   | Tỷ lệ lặp lại: 35%     |
|-----------------------------------------------------------|
| [Doanh thu theo giờ] [Top sản phẩm] [Khách hàng quay lại] |
|-----------------------------------------------------------|
| 7 ngày gần nhất | 30 ngày gần nhất | Top nhóm hàng       |
+-----------------------------------------------------------+
```

### 3.2 Màn hình tạo chiến dịch quảng cáo

```text
+-----------------------------------------------------------+
| Tạo chiến dịch quảng cáo                                  |
|-----------------------------------------------------------|
| Nền tảng: [Facebook Ads] [Google Ads]                    |
| Mục tiêu: [Tăng bán hàng] [Tăng lưu lượng]                |
| Đối tượng: [Quận/Huyện] [Ngành hàng] [Tuổi] [Giới tính] |
| Ngân sách: 10,000,000 ₫ / ngày                            |
| Nội dung quảng cáo: [Text + Image + CTA]                  |
|-----------------------------------------------------------|
| [Lưu nháp] [Xem trước] [Đăng chiến dịch]                  |
+-----------------------------------------------------------+
```

### 3.3 Campaign performance screen

```text
+-----------------------------------------------------------+
| Campaign Performance                                     |
|-----------------------------------------------------------|
| Total spend | 2.4M ₫ | ROI: 18% | CPA: 85K ₫            |
|-----------------------------------------------------------|
| [Conversion chart] [ROI chart] [Top-performing channel] |
|-----------------------------------------------------------|
| Facebook Ads: 12.4% CTR | Google Ads: 8.2% CTR          |
+-----------------------------------------------------------+
```

### 3.4 Wizard hóa đơn điện tử

```text
+-----------------------------------------------------------+
| Tạo hóa đơn điện tử                                      |
|-----------------------------------------------------------|
| Bước 1: Chọn giao dịch                                   |
| Bước 2: Kiểm tra thông tin khách hàng                    |
| Bước 3: Xác nhận thuế và nộp hồ sơ                       |
|-----------------------------------------------------------|
| [Quay lại] [Tiếp tục] [Hoàn thành]                        |
+-----------------------------------------------------------+
```

### 3.5 Sơ đồ thành phần UI

```mermaid
graph TB
    A[Dashboard Card] --> B[Shared Components]
    C[Campaign Builder] --> B
    D[Analytics Panel] --> B
    E[Invoice Wizard] --> B
    B --> F[Button / Modal / Table / Chart]
```

---

## 4. Mô hình dữ liệu và mapping UI

### 4.1 Mô hình dữ liệu chính

```mermaid
graph TB
    subgraph "Dữ liệu giao dịch"
        T[transactions]
    end

    subgraph "Phân tích bán hàng"
        S[sales_summary]
        C[customer_profile]
    end

    subgraph "Marketing"
        A[ads_campaigns]
        M[ads_metrics]
    end

    subgraph "Hóa đơn"
        I[invoices]
        X[tax_summary]
    end

    T --> S
    T --> C
    C --> A
    A --> M
    T --> I
    I --> X
```

### 4.2 UI → data mapping

| UI screen | Data source | Key fields |
|---|---|---|
| Revenue dashboard | sales_summary | revenue_today, revenue_week, target_progress |
| Campaign builder | ads_campaigns | campaign_name, platform, budget, objective |
| Ad analytics | ads_metrics | ctr, cpa, conversions, roi |
| Invoice wizard | invoices | invoice_id, amount, tax_amount, status |

### 4.3 Mô hình dữ liệu rút gọn

```sql
CREATE TABLE ads_campaigns (
    campaign_id VARCHAR(50) PRIMARY KEY,
    merchant_id VARCHAR(50),
    platform VARCHAR(20),
    objective VARCHAR(50),
    budget BIGINT,
    status VARCHAR(20)
);

CREATE TABLE ads_metrics (
    campaign_id VARCHAR(50) PRIMARY KEY,
    impressions INT,
    clicks INT,
    conversions INT,
    cpa BIGINT,
    roi DECIMAL(5,2)
);

CREATE TABLE invoices (
    invoice_id VARCHAR(50) PRIMARY KEY,
    merchant_id VARCHAR(50),
    txn_id VARCHAR(50),
    amount BIGINT,
    tax_amount BIGINT,
    status VARCHAR(20)
);
```

### 4.4 Luồng dữ liệu chủ đạo

```mermaid
graph LR
    A[QR payment] --> B[Transaction Store]
    B --> C[Sales Summary]
    B --> D[Customer Profile]
    C --> E[Dashboard]
    D --> F[Facebook Ads / Google Ads]
    F --> G[Ads Metrics]
    B --> H[Invoice Engine]
    H --> I[Tax Summary]
```

---

## 5. JD Mapping & Interview Prep

### 5.1 Góc nhìn sản phẩm cho JD này

```mermaid
flowchart TB
    A["Vấn đề cốt lõi<br/>merchant lo lắng về tiền"] --> B["Tin tưởng + Chứng minh"]
    B --> C["Đối soát minh bạch"]
    B --> D["Hiểu doanh thu bằng ngôn ngữ đơn giản"]
    B --> E["AI Moni hỗ trợ quyết định"]
    C --> F["An tâm"]
    D --> F
    E --> F

    style A fill:#E3F2FD,stroke:#1565C0,stroke-width:2px
    style B fill:#FFF3E0,stroke:#EF6C00,stroke-width:2px
    style C fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px
    style D fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px
    style E fill:#E0F7FA,stroke:#00838F,stroke-width:2px
    style F fill:#FFEBEE,stroke:#C62828,stroke-width:2px
```

### 5.2 Merchant journey nhanh

```mermaid
flowchart LR
    A["Khách hàng thanh toán"] --> B["Giao dịch vào hệ thống"]
    B --> C["Sổ Thu Chi / Widget Home"]
    C --> D["Merchant thấy rõ doanh thu"]
    D --> E["Tăng trust + quay lại dùng"]
    E --> F["Mở rộng bán hàng & tiếp cận vốn"]

    style A fill:#FFF8E1,stroke:#F9A825,stroke-width:2px
    style B fill:#E3F2FD,stroke:#1565C0,stroke-width:2px
    style C fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px
    style D fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px
    style E fill:#E0F7FA,stroke:#00838F,stroke-width:2px
    style F fill:#FFEBEE,stroke:#C62828,stroke-width:2px
```

### 5.3 Metrics loop for product

```mermaid
flowchart TB
    A["Tương tác"] --> B["Giữ chân"]
    B --> C["Chuyển đổi"]
    C --> D["Monetization"]
    D --> E["Niềm tin merchant"]
    E --> A

    style A fill:#E3F2FD,stroke:#1565C0,stroke-width:2px
    style B fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px
    style C fill:#FFF3E0,stroke:#EF6C00,stroke-width:2px
    style D fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px
    style E fill:#FFEBEE,stroke:#C62828,stroke-width:2px
```

### 5.4 Cross-functional execution

```mermaid
graph LR
    P["Sản phẩm"] --> E["Kỹ thuật"]
    P --> D["Dữ liệu"]
    P --> A["AI"]
    P --> X["Thiết kế"]
    P --> O["Vận hành"]
    E --> R["Ra mắt"]
    D --> R
    A --> R
    X --> R
    O --> R

    style P fill:#E3F2FD,stroke:#1565C0,stroke-width:2px
    style E fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px
    style D fill:#FFF3E0,stroke:#EF6C00,stroke-width:2px
    style A fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px
    style X fill:#E0F7FA,stroke:#00838F,stroke-width:2px
    style O fill:#FFEBEE,stroke:#C62828,stroke-width:2px
    style R fill:#FCE4EC,stroke:#C2185B,stroke-width:2px
```

### 5.5 Short concise Q&A for interview

- Q: What is this JD about?  
  A: Build merchant-first products that help SMEs trust their cash flow, understand their business, and grow through better insights and AI assistance.

- Q: Why is merchant engagement important?  
  A: Because merchants need confidence, not just features. If they trust the product, they will use it more often and stay longer.

- Q: How would you approach user research?  
  A: Start with field interviews, observe older and less tech-savvy merchants, and turn their language into clear user stories.

- Q: What metrics matter most?  
  A: Engagement, retention, conversion, revenue impact, and stability after release.

- Q: How would you prioritize features?  
  A: Use Jobs-to-be-Done: solve trust + proof first, then simplify the experience and remove friction.

- Q: What role does AI play?  
  A: AI should make work easier, not more complicated. Moni should help merchants act faster with simple and useful suggestions.

- Q: What makes a good product trainee here?  
  A: Curiosity, proactivity, empathy for merchants, strong communication, and ability to turn data into action.

### 5.6 Short concise solution answer

**Product thesis:** turn every QR payment into trusted evidence, simple insight, and useful next actions for merchants.

```mermaid
flowchart TB
    A["Merchant pain<br/>unclear cash flow"] --> B["Trust layer<br/>proof + reconciliation"]
    B --> C["Insight layer<br/>dashboard + AI"]
    C --> D["Action layer<br/>invoice / ads / advice"]
    D --> E["Outcome<br/>peace of mind + growth"]

    style A fill:#E3F2FD,stroke:#1565C0,stroke-width:2px
    style B fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px
    style C fill:#FFF3E0,stroke:#EF6C00,stroke-width:2px
    style D fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px
    style E fill:#FFEBEE,stroke:#C62828,stroke-width:2px
```

```mermaid
flowchart LR
    A["Merchant opens app"] --> B["Sees today revenue"]
    B --> C["Checks cash flow"]
    C --> D["Auto invoice"]
    C --> E["AI suggestion"]
    D --> F["Confidence"]
    E --> F

    style A fill:#FFF8E1,stroke:#F9A825,stroke-width:2px
    style B fill:#E3F2FD,stroke:#1565C0,stroke-width:2px
    style C fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px
    style D fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px
    style E fill:#E0F7FA,stroke:#00838F,stroke-width:2px
    style F fill:#FFEBEE,stroke:#C62828,stroke-width:2px
```

```mermaid
sequenceDiagram
    participant M as Merchant
    participant P as MoMo
    participant AI as Moni

    M->>P: Receive QR payment
    P->>P: Record transaction
    P->>M: Show daily recap
    P->>AI: Detect pattern
    AI-->>M: Suggest next action
```

```mermaid
flowchart TB
    A["Adoption"] --> B["Engagement"]
    B --> C["Retention"]
    C --> D["Monetization"]
    D --> E["Trust"]
    E --> A

    style A fill:#E3F2FD,stroke:#1565C0,stroke-width:2px
    style B fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px
    style C fill:#FFF3E0,stroke:#EF6C00,stroke-width:2px
    style D fill:#F3E5F5,stroke:#6A1B9A,stroke-width:2px
    style E fill:#FFEBEE,stroke:#C62828,stroke-width:2px
```

**Why this fits the JD:**
- Trust + Proof: help merchants feel secure about every transaction.
- Simplicity: make the experience clear for older, less tech-savvy users.
- AI + data: turn behavior signals into daily recommendations.
- Execution: connect product, data, design, engineering, and ops around one merchant goal.

---

## 6. Roadmap triển khai

```mermaid
timeline
    title Roadmap SME Merchants 2026-2027
    section Q2 2026
        Dashboard MVP
        : Doanh thu theo thời gian
        : Mục tiêu và cảnh báo
    section Q3 2026
        Growth Marketing
        : Facebook Ads
        : Google Ads
        : ROI tracking
    section Q4 2026
        Compliance
        : Hóa đơn điện tử
        : Tự động tính thuế
    section Q1 2027
        Scale-up
        : AI recommendation
        : Tự động tối ưu ngân sách quảng cáo
```

---

**Phiên bản**: 2.1  
**Ngày cập nhật**: 15/07/2026  
**Trạng thái**: Sẵn sàng cho kickoff engineering và phỏng vấn
