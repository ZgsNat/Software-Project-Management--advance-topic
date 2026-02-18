# SOFTWARE REQUIREMENTS SPECIFICATION (SRS) - SDS PROJECT

## Feature 1: Smart Booking and Allotment Management

## Feature 2: Automated Customer Support (AI Chatbot)

**Version: 1.2** 
**Status: Finalized**
**Date: 18/02/2026**
---

### 1. Introduction

#### 1.1 Purpose

Đặc tả chi tiết luồng nghiệp vụ và quy tắc hệ thống cho hai tính năng trọng tâm: Đặt lịch học lái xe thông minh (tối ưu hóa phân bổ) và Hệ thống hỗ trợ khách hàng tự động thông qua AI Chatbot.

#### 1.2 Scope

Bao gồm các module chính:

* **Module Đặt lịch:** Quản lý lịch trống (Availability), Đặt chỗ (Booking), Phân bổ thông minh (Smart Allotment) và Dự báo (Forecasting).
* **Module Chatbot:** Giao diện Chat, Xử lý ngôn ngữ tự nhiên (NLP), Tích hợp cơ sở tri thức (RAG) và API Booking.

---

### 2. Actor Description

| Actor name | Description |
| --- | --- |
| **Learner Driver** | Người đăng ký học, có trình độ (Level) và lịch sử học tập cụ thể. |
| **Instructor** | Người trực tiếp hướng dẫn, có lịch làm việc và danh sách học viên phụ trách. |
| **AI Engine** | Tác nhân hệ thống: Phân tích dữ liệu để dự báo, tối ưu ghép nhóm và xử lý ngôn ngữ. |
| **Chatbot System** | Tác nhân hệ thống: Tiếp nhận hội thoại, truy xuất Knowledge Base và gọi API. |
| **Admin** | Người giám sát toàn bộ lịch trình, quản lý Knowledge Base và phê duyệt điều động nhân sự. |

---

### 3. User Stories

* **US-01:** Là một học viên, tôi muốn đặt lịch học trực tuyến để tôi có thể chủ động sắp xếp thời gian cá nhân.
* **US-02:** Là một học viên, tôi muốn hệ thống gợi ý các khung giờ mà tôi có thể thực hành nhiều nhất hoặc cùng trình độ với các bạn khác.
* **US-03:** Là một giảng viên, tôi muốn xem lịch dạy hàng tuần để chuẩn bị giáo án và xe phù hợp.
* **US-04:** Là một giảng viên, tôi muốn biết trình độ của 3 học viên trong cùng một ca để có phương pháp hướng dẫn tối ưu.
* **US-05:** Là một quản trị viên, tôi muốn biết dự báo số lượng học viên trong 2 tuần tới để điều động đủ số lượng giảng viên trực.
* **US-06:** Là một học viên, tôi muốn hỏi về các thủ tục đăng ký để tôi có thể chuẩn bị hồ sơ nhanh chóng.
* **US-07:** Là một học viên, tôi muốn nhận được phản hồi hỗ trợ ngay lập tức vào ban đêm khi nhân viên văn phòng đã nghỉ làm.
* **US-08**: Là một học viên, tôi muốn chatbot cho biết tiến độ học tập (số giờ đã lái, bài học tiếp theo) để tôi nắm rõ lộ trình.
* **US-09**: Là một học viên, tôi muốn hỏi chatbot về các khoản học phí còn nợ hoặc biểu phí khóa học nâng cao.
* **US-10:** Là một học viên, tôi muốn chatbot cho biết lịch học của tôi mà không cần truy cập dashboard.
* **US-11:** Là một học viên, tôi muốn chatbot trả lời chính xác theo quy định chính thức của trung tâm.

---

### 4. User Case Description

#### UC-01 – Book Training Session

| **Field** | **Details** |
| --- | --- |
| **UC ID and Name** | UC-01 – Book Training Session |
| **Primary Actor** | Learner Driver |
| **Secondary Actor** | AI Engine |
| **Trigger** | Học viên chọn chức năng "Đặt lịch học" trên ứng dụng |
| **Description** | Học viên chọn ngày, giờ và hệ thống kiểm tra tính khả dụng, đồng thời AI gợi ý slot tối ưu |
| **Preconditions** | Học viên đã đăng nhập và tài khoản còn số dư buổi học hợp lệ |
| **Postconditions** | Một bản ghi Booking mới được tạo, trạng thái Slot được cập nhật |
| **Normal Flow** | 1. Học viên chọn ngày mong muốn<br>2. Hệ thống hiển thị danh sách khung giờ<br>3. AI Engine đánh dấu "Gợi ý tốt nhất"<br>4. Học viên chọn khung giờ<br>5. Hệ thống kiểm tra ràng buộc<br>6. Hệ thống xác nhận đặt lịch |
| **Alternative Flows** | A1: Đổi lịch (hủy lịch cũ trước, nếu <24h thì áp dụng phí) |
| **Exceptions** | E1: Slot đã đủ 3 người<br><br>E2: Giảng viên gặp sự cố, session chuyển sang "Pending Re-assignment" |
| **Priority** | High |
| **Business Rules** | BR-01, BR-02, BR-03, BR-04, BR-05 |

---

#### UC-02 – Training Demand Forecasting (AI Driven)

| **Field**        | **Details** |
|------------------|-------------|
| **UC ID and Name**   | UC-02 – Training Demand Forecasting |
| **Primary Actor**    | System Admin |
| **Secondary Actor**  | AI Engine |
| **Trigger**          | Admin truy cập Dashboard báo cáo hoặc định kỳ hàng tuần |
| **Description**      | Hệ thống phân tích dữ liệu lịch sử để dự báo số lượng học viên và giảng viên cần thiết |
| **Preconditions**    | Admin có quyền truy cập Dashboard |
| **Postconditions**   | Biểu đồ dự báo hiển thị cho Admin |
| **Normal Flow**      | 1. AI Engine truy xuất dữ liệu booking lịch sử và xu hướng đăng ký mới<br>2. AI tính toán số lượng ca học dự kiến cho tuần/tháng tiếp theo<br>3. Hệ thống tính toán số lượng giảng viên cần thiết tương ứng<br>4. Hệ thống đối soát với danh sách Instructor khả dụng hiện tại và đưa ra cảnh báo nếu nguồn lực không đủ đáp ứng nhu cầu dự báo<br>5. Hệ thống hiển thị biểu đồ dự báo và các đề xuất điều động cho Admin. |
| **Alternative Flows**| Không có |
| **Exceptions**       | Không có |
| **Priority**         | Medium |
| **Business Rules**   | BR-01, BR-02, BR-03 |

---

#### UC-03 – Process Customer Inquiry

| **Field** | **Details** |
| --- | --- |
| **UC ID and Name** | UC-03 – Process Customer Inquiry |
| **Primary Actor** | Learner Driver |
| **Secondary Actor** | Chatbot System |
| **Trigger** | Học viên gửi tin nhắn vào khung chat hỗ trợ |
| **Description** | Chatbot phân tích câu hỏi, truy xuất thông tin từ cơ sở tri thức hoặc API để phản hồi học viên |
| **Preconditions** | Hệ thống Chatbot đang hoạt động (Online) |
| **Postconditions** | Học viên nhận được câu trả lời; Lịch sử hội thoại được lưu lại |
| **Normal Flow** | 1. User gửi message<br>2. Chatbot phân tích intent (ý định)<br>3. Chatbot truy vấn Knowledge Base (Vector Search)<br>4. Chatbot tạo response dựa trên dữ liệu tìm thấy<br>5. Response trả về cho user |
| **Alternative Flows** | A1 – Booking Query: Intent là tra cứu lịch -> Chatbot gọi Booking API -> Trả kết quả cho User |
| **Exceptions** | E1 – No answer: AI không chắc chắn -> Phản hồi xin lỗi và đề xuất liên hệ nhân viên/kiểm tra Dashboard |
| **Priority** | High |
| **Business Rules** | BR-06, BR-07, BR-08 |

---

### 5. Functional Requirements (FR)

* **FR-01 (Booking):** Hệ thống phải cho phép học viên đặt lịch tối thiểu trước 12 giờ trước khi buổi học bắt đầu.
* **FR-02 (Allotment Control):** Hệ thống phải đảm bảo không bao giờ vượt quá 3 học viên trong cùng một ca học 1 giờ.
* **FR-03 (Instructor Assignment):** Hệ thống tự động gán giảng viên dựa trên lịch trống và chuyên môn (xe số/xe tự động).
* **FR-04 (Smart Grouping):** AI ưu tiên xếp các học viên cùng tiến độ bài học vào cùng một ca để tối ưu hóa việc hướng dẫn.
* **FR-05 (Forecasting Alert)**: Hệ thống phải đưa ra cảnh báo đỏ (Alert) trên dashboard nếu dự báo nhu cầu vượt quá khả năng phục vụ của đội ngũ giảng viên hiện có.
* **FR-06 (Notification):** Hệ thống gửi thông báo (Push/Email) ngay khi lịch học được xác nhận hoặc thay đổi.
* **FR-07 (NLU):** Hệ thống phải nhận diện được ý định (Intent) của người dùng thông qua ngôn ngữ tự nhiên.
* **FR-08 (RAG Integration):** Hệ thống phải truy xuất chính xác thông tin từ Knowledge Base đã được phê duyệt.
* **FR-09 (API Integration):** Chatbot phải có khả năng gọi API để kiểm tra trạng thái booking và lịch học cá nhân.
* **FR-10 (Progress Tracking Query)**: Hệ thống phải hỗ trợ Chatbot truy vấn và phản hồi thông tin về tiến độ học tập của học viên từ Database.
* **FR-11 (Conversation Logging):** Mọi cuộc hội thoại phải được lưu nhật ký để phục vụ kiểm soát chất lượng.

---

### 6. Non-Functional Requirements (NFR)

* **NFR-01 (Performance):** Thời gian phản hồi khi tìm kiếm slot trống phải dưới 2 giây.
* **NFR-02 (Concurrency):** Xử lý ít nhất 50 yêu cầu đặt lịch đồng thời không gây "Double Booking".
* **NFR-03 (Latency):** Thời gian phản hồi của Chatbot phải dưới 3 giây.
* **NFR-04 (Capacity):** Hỗ trợ tối thiểu 100 cuộc hội thoại đồng thời.
* **NFR-05 (Availability):** Hệ thống (Booking & Chatbot) phải hoạt động 24/7.
* **NFR-06 (Security):** Mã hóa thông tin cá nhân trong các cuộc hội thoại được lưu trữ.
* **NFR-07 (API Uptime):** Booking API phục vụ Chatbot phải có uptime tối thiểu 99.9%.

---

### 7. Business Rules (BR)

* **BR-01 (Duration):** Một ca học tiêu chuẩn kéo dài chính xác 60 phút.
* **BR-02 (Capacity):** Một ca học chỉ được phép có tối đa 3 học viên tham gia.
* **BR-03 (Cancellation):** Hủy lịch miễn phí trước 24 giờ. Hủy sau 24 giờ sẽ bị trừ 1 buổi học.
* **BR-04 (Mandatory Association):** Mọi ca học phải được liên kết với ít nhất 1 giảng viên và 1 xe tập lái cụ thể.
* **BR-05 (Official Source Only):** Chatbot chỉ được trả lời dựa trên dữ liệu chính thức, không được tự tạo thông tin không có trong Knowledge Base.
* **BR-06 (Data Integrity):** Chatbot chỉ có quyền đọc dữ liệu Booking, không được trực tiếp sửa đổi dữ liệu qua hội thoại.
* **BR-07 (Language):** Ưu tiên xử lý ngôn ngữ Tiếng Việt làm ngôn ngữ mặc định.

---
