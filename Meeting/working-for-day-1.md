# Nhiệm vụ team Dev & Ba [T + H] sprint 1

## Tổng thể nhiệm vụ


* Mục tiêu:
  → Tạo tài liệu đặc tả để:

  * Leader tiếp tục design
  * Tester tạo test cases
  * Dev có thể implement

---

### 1. Xác định Actors

Cho 2 feature:

Smart Booking:

* Learner Driver
* Instructor
* Admin

Chatbot:

* Learner
* Chatbot System
* Admin (optional)

**Deliverable:** Actors list

---

### 2. Viết User Stories

Ví dụ:

Smart Booking:

* As a learner, I want to book a training session
* As an instructor, I want to set my availability
* As a system, I want to assign learners to sessions

Chatbot:

* As a learner, I want to ask questions
* As a system, I want to respond automatically

**Deliverable:** User Stories list

---

### 3. Viết Use Cases

Ví dụ:

Use Case: Book training session

Flow:

1. Learner selects date
2. System shows available slots
3. Learner selects slot
4. System confirms booking

**Deliverable:** Use Case descriptions

---

### 4. Viết Functional Requirements (core của SRS)

Ví dụ:

FR-1: System shall allow learners to book training sessions

FR-2: System shall assign instructor automatically

FR-3: System shall limit session capacity to 3 learners

FR-4: Chatbot shall respond to learner questions

**Deliverable:** Functional Requirements list

---

### 5. Define Business Rules

Ví dụ:

* Session duration = 1 hour
* Max 3 learners per session
* Instructor must be available
* Cannot double-book instructor

**Deliverable:** Business Rules list

---

### 6. Organize tất cả thành SRS document

Structure cuối cùng:

```
SRS
 ├ Introduction
 ├ Actors
 ├ User Stories
 ├ Use Cases
 ├ Functional Requirements
 └ Business Rules
```

---

# Phân chia công việc tối ưu giữa bạn và chị Hoa

Chị Hoa (BA focus):

* Actors
* User Stories
* Use Cases (business flow)

Bạn (Dev/System focus):

* Functional Requirements
* Business Rules
* System behavior logic
* Review toàn bộ SRS

---

# Deliverable cuối Sprint này

Một tài liệu:

```
Software Requirements Specification (SRS)
```

cho 2 feature:

* Smart Booking & Allotment
* Chatbot

---

# Mục tiêu của SRS này

Sẽ được dùng bởi:

Leader → để design system
Tester → để tạo test cases
Dev → để implement

---

# Tóm tắt cực ngắn

Trong Sprint này, bạn và chị Hoa sẽ:

* Identify actors
* Write user stories
* Write use cases
* Write functional requirements
* Define business rules
* Compile SRS document

---

Nếu bạn muốn, tôi có thể đưa bạn **checklist chính xác từng mục phải có trong SRS để đạt điểm tối đa theo rubric**.
