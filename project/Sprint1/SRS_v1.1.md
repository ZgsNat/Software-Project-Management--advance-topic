# SOFTWARE REQUIREMENTS SPECIFICATION (SRS) - SDS PROJECT

Version: 1.1  
Status: Draft – Architect Level  
Last Updated: 2026-02-18  

---

# Feature 1: Smart Booking and Allotment Management

## 1. Introduction

### 1.1 Purpose

Đặc tả chi tiết luồng nghiệp vụ và quy tắc hệ thống cho tính năng đặt lịch học lái xe thông minh, tối ưu phân bổ giảng viên và dự báo nhu cầu đào tạo.

### 1.2 Scope

Bao gồm các module:

- Availability Management
- Booking Management
- Smart Allotment Engine
- Forecasting Engine
- Notification Service

Hệ thống cũng cung cấp API để tích hợp với các module khác như Automated Customer Support (AI Chatbot).

---

## 2. Actor Description

| Actor name | Description |
|-----------|-------------|
| Learner Driver | Người đăng ký học, có trình độ và lịch sử học tập |
| Instructor | Người trực tiếp hướng dẫn |
| AI Engine | Phân tích dữ liệu và tối ưu hóa phân bổ |
| Admin | Giám sát và điều phối hệ thống |

---

## 3. User Stories

US-01 → US-05 giữ nguyên như Version 1.0.

---

## 4. Use Case Description

UC-01 và UC-02 giữ nguyên như Version 1.0.

---

## 5. Functional Requirements

FR-01 → FR-06 giữ nguyên.

FR-17 (External API Support)  
Hệ thống phải cung cấp API an toàn để các hệ thống nội bộ khác (ví dụ Chatbot) truy vấn:

- Booking status
- Schedule availability
- Learner booking history

---

## 6. Non Functional Requirements

NFR-01 → NFR-04 giữ nguyên.

NFR-09 (API Availability)  
Booking API phải có uptime tối thiểu 99.9%.

---

## 7. Business Rules

BR-01 → BR-05 giữ nguyên.

---

# Feature 2: Automated Customer Support (AI Chatbot)

## 1. Introduction

### 1.1 Purpose

Cung cấp hệ thống hỗ trợ khách hàng tự động 24/7 cho học viên SDS, có khả năng:

- hiểu ngôn ngữ tự nhiên
- truy xuất Knowledge Base
- gọi Booking API
- trả lời chính xác theo dữ liệu chính thức

### 1.2 Scope

Bao gồm:

- Chat Interface
- NLP Processing Engine
- Knowledge Base Integration (RAG)
- Booking API Integration
- Conversation Context Management
- Conversation Logging

Không bao gồm Ticket System trong Version 1.1.

---

## 2. Actor Description

| Actor name | Description |
|-----------|-------------|
| Learner Driver | Người dùng chatbot |
| Chatbot System | AI xử lý hội thoại |
| Admin | Quản lý Knowledge Base |

---

## 3. User Stories

US-06 → US-09 giữ nguyên từ draft.

US-10  
Là học viên, tôi muốn chatbot cho biết lịch học của tôi.

US-11  
Là học viên, tôi muốn chatbot trả lời chính xác theo quy định chính thức.

---

## 4. Use Case Description

### UC-03 – Process Customer Inquiry

Primary Actor: Learner Driver  
Secondary Actor: Chatbot System  

Normal Flow:

1. User gửi message
2. Chatbot phân tích intent
3. Chatbot truy vấn Knowledge Base (Vector Search)
4. Chatbot tạo response
5. Response trả về user

Alternative Flow A1 – Booking Query:

1. Intent nhận diện là booking query
2. Chatbot gọi Booking API
3. API trả dữ liệu
4. Chatbot trả lời

Exception E1 – No answer:

Chatbot trả lời không chắc chắn và đề xuất user kiểm tra dashboard.

---

## 5. Functional Requirements

FR-07 Natural Language Understanding  
FR-08 Knowledge Base Integration (RAG)  
FR-09 Booking API Integration (Direct Option A)  
FR-10 Conversation Context (Optional implementation supported)  
FR-11 Conversation Logging  
FR-12 Abuse Protection  
FR-13 Confidence Threshold Handling  

---

## 6. Non Functional Requirements

NFR-05 Response latency < 3 seconds  
NFR-06 Support 100 concurrent chats  
NFR-07 Availability 24/7  
NFR-08 Encryption for stored conversations  
NFR-10 Horizontal Scalability  

---

## 7. Business Rules

BR-06 Official Source Only  
BR-07 Chatbot must not generate unsupported information  
BR-08 Vietnamese Language Priority  

---

# Integration Requirements

IR-01 Chatbot must use Booking API only via authenticated requests.

IR-02 Chatbot must not violate booking constraints defined in Feature 1.

IR-03 Chatbot must not modify booking data directly.

IR-04 Chatbot is read-only client of Booking Service.

---

End of Document
