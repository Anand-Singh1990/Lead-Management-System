# 🧠 Lead Management System (LMS)

A scalable, field-configurable system to manage lead capture, approval workflows, EMI logic, and partner mapping. Designed to support multiple business lines and reduce lead management overhead across distributed teams.

---

## 📌 Problem Statement

In fast-paced B2B/B2C environments, lead flows differ by product, partner, and business unit. Rigid schema and manual handling led to:

- Delayed approval cycles
- Frequent data mismatches
- Developer dependency for field updates

We needed a modular system to:
- Accept leads from multiple sources
- Allow admin-driven field configuration (no code changes)
- Route leads dynamically to approval flows and partners
- Scale with 10K+ monthly leads

---

## ⚙️ Tech Stack

- **Backend:** Django, Django REST Framework  
- **Databases:** MongoDB (for flexible lead schema), MySQL (for structured tracking)  
- **Queue/Async:** Celery, Redis  
- **Auth:** JWT, Role-Based Access Control (RBAC)  
- **Infra:** Docker, Nginx  
- **Optional:** AWS S3 for file/document uploads (KYC, quotes, etc.)

---

## 🚀 Key Features

### 🧱 Dynamic Field Engine
- Admin-defined schema builder (label, type, validations, required/optional)
- Separate field config per product line (e.g., loans, insurance, partner leads)
- Stored in MongoDB for flexible structure

### 🔁 Lead Intake Pipelines
- APIs for direct partner ingestion
- Internal dashboards (multi-role forms)
- File-based lead ingestion via Celery jobs (Excel, CSV)

### ✅ Approval Workflow Engine
- Configurable multi-step approval per lead type
- State transitions tracked via MySQL with audit logs
- Manual + rule-based approval triggers

### 💳 EMI & Partner Routing
- EMI logic based on tenure, amount, and partner rules
- Rule-based lead distribution (50+ partners)
- Fallback logic in case of partner disqualification

### 📊 Analytics & Internal Reporting
- Dashboard with filters (status, partner, region, timeline)
- Team-level performance breakdown
- Field-level distribution stats for ops/product teams

---

## 📈 Impact

| Metric | Result |
|--------|--------|
| 📥 Leads Processed | 10K+ / month |
| ⚙️ Field Variants Supported | 100+ |
| ⏱️ Approval Time Reduced | 30% faster |
| 🧾 Data Integrity | 98.5%+ accuracy |
| 🧩 Partner Routing | 50+ integrated |

---

## 📂 Architecture Flow
User / API / File Upload
↓
Field Config Loader ← Admin-defined schema (MongoDB)
↓
Lead API (Django DRF) → Validation Layer
↓
Queue (Celery) for ingestion / mapping / approval
↓
Approval Tracker (MySQL)
↓
Partner Router / EMI Logic → Partner API or queue
↓
Status Update + Dashboard Metrics

---

## 🧠 Takeaways

- Learned to design highly flexible systems using hybrid DBs (Mongo + MySQL)  
- Built a zero-code field configurator — enabling ops to update flows independently  
- Enabled async ingestion and dynamic routing — removing bottlenecks  
- Handled real-world partner-level routing logic at scale  
- Designed APIs and dashboards used by multiple business verticals

---

## 📌 Note

This case study is based on a production system built at a fintech startup. Source code is confidential; however, structure, logic, and impact reflect real implementation.
