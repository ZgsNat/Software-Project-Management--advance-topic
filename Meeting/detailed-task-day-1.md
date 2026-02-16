Dưới đây là **phiên bản cập nhật thành checklist công việc cụ thể bạn và chị Hoa có thể làm ngay, và ghi trực tiếp vào file markdown**, phù hợp với:

* Case study Smart Driving School (SDS)
* 2 features: Smart Booking & Chatbot
* Rubric yêu cầu: design spec + test spec + agile artifacts
* Không cần call, vẫn phối hợp được

---

# Nhiệm vụ team Dev & BA [T + H] — Sprint 1 (Execution Checklist)

## Mục tiêu Sprint

Tạo **SRS hoàn chỉnh (draft version)** cho 2 features:

* Smart Booking & Allotment Management
* Automated Customer Support (Chatbot)

SRS này sẽ được dùng bởi:

* Leader → tạo Design specification
* Tester → tạo Test cases
* Dev → implement system

---

# Phần 1 — Xác định Actors

## Công việc cần làm

Tạo section trong markdown:

```
## Actors
```

Cho mỗi feature, ghi:

Format:

```
Actor Name:
Description:
Goals:
```

---

## Smart Booking — cần viết

```
Actor: Learner Driver
Description: Người học lái xe đăng ký training session
Goals:
- Book training session
- View booked sessions
- Cancel booking
```

```
Actor: Instructor
Description: Người dạy lái xe
Goals:
- View assigned sessions
- Manage availability
```

```
Actor: Admin
Description: Người quản lý hệ thống
Goals:
- Manage instructors
- View system schedule
```

---

## Chatbot — cần viết

```
Actor: Learner Driver
Actor: Chatbot System
Actor: Admin (optional)
```

---

## Người thực hiện

Chị Hoa viết
Bạn review + chỉnh technical accuracy

---

# Phần 2 — Viết User Stories

## Tạo section

```
## User Stories
```

---

## Format chuẩn

```
US-1:
As a <actor>
I want to <action>
So that <benefit>
```

---

## Smart Booking — cần viết ít nhất 5–8 user stories

Ví dụ:

```
US-1:
As a learner driver
I want to book a training session
So that I can learn driving
```

```
US-2:
As a learner driver
I want to view available sessions
So that I can choose a suitable time
```

```
US-3:
As an instructor
I want to view my schedule
So that I know my teaching sessions
```

---

## Chatbot — cần viết 4–6 stories

Ví dụ:

```
US-9:
As a learner
I want to ask questions
So that I get information quickly
```

---

## Người thực hiện

Chị Hoa viết
Bạn bổ sung các system-level stories nếu thiếu

---

# Phần 3 — Viết Use Cases

## Tạo section

```
## Use Cases
```

---

## Format chuẩn

```
Use Case ID: UC-1
Name: Book training session

Actor: Learner Driver

Preconditions:
- Learner is logged in

Main Flow:
1. Learner selects date
2. System shows available sessions
3. Learner selects session
4. System confirms booking

Alternative Flow:
A1: No available session
→ System shows message

Postconditions:
- Booking is created
```

---

## Smart Booking cần ít nhất:

* UC-1 Book session
* UC-2 View sessions
* UC-3 Cancel session
* UC-4 Assign instructor (system/admin)

---

## Chatbot cần:

* UC-5 Ask question
* UC-6 Receive response

---

## Người thực hiện

Chị Hoa viết flow
Bạn thêm system behavior nếu thiếu

---

# Phần 4 — Functional Requirements

## Tạo section

```
## Functional Requirements
```

---

## Format chuẩn

```
FR-1: System shall allow learner drivers to book training sessions.

FR-2: System shall display available sessions.

FR-3: System shall assign instructors to sessions.

FR-4: System shall prevent overbooking.

FR-5: Chatbot shall respond to learner questions.
```

---

## Quan trọng

Mỗi User Story → ít nhất 1 Functional Requirement

---

## Người thực hiện

Bạn viết phần này (Dev/System responsibility)

---

# Phần 5 — Business Rules

## Tạo section

```
## Business Rules
```

---

## Viết rules từ case study SDS

Ví dụ:

```
BR-1: A training session duration is 1 hour.

BR-2: A session can have maximum 3 learner drivers.

BR-3: An instructor cannot be assigned to overlapping sessions.

BR-4: Booking must be associated with a learner and session.

BR-5: Chatbot must provide automated responses.
```

---

## Người thực hiện

Bạn viết phần này

---

# Phần 6 — Organize thành SRS document hoàn chỉnh

Markdown structure cuối cùng:

```
SRS.md

# Software Requirements Specification

## 1. Introduction

## 2. Actors

## 3. User Stories

## 4. Use Cases

## 5. Functional Requirements

## 6. Business Rules
```

---

# Phân chia công việc cụ thể giữa bạn và chị Hoa

## Chị Hoa làm

```
Actors
User Stories
Use Cases
```

## Bạn làm

```
Functional Requirements
Business Rules
Review toàn bộ SRS
Fix technical logic
Ensure consistency
```

---

# Deliverable cuối Sprint này

File:

```
SRS.md
```

cho:

* Smart Booking
* Chatbot

---

# Definition of Done (để đạt điểm cao theo rubric)

Sprint này hoàn thành khi:

* Actors defined
* User stories complete
* Use cases complete
* Functional requirements complete
* Business rules complete
* SRS organized cleanly
* Leader và Tester có thể đọc và hiểu để làm tiếp

---

Nếu bạn muốn, tôi có thể viết luôn **SRS.md hoàn chỉnh cho Smart Booking để bạn chỉ cần chỉnh sửa và nộp**, tiết kiệm 80% thời gian.
