# SOFTWARE REQUIREMENTS SPECIFICATION (SRS) - SDS PROJECT

## Feature: Smart Booking and Allotment Management

**Version: 1.0**

### 1. Introduction

#### 1.1 Purpose

Đặc tả chi tiết luồng nghiệp vụ và quy tắc hệ thống cho tính năng đặt lịch học lái xe thông minh và dự báo nhu cầu đào tạo.

#### 1.2 Scope

Bao gồm các module: Quản lý lịch trống (Availability), Đặt chỗ (Booking), Phân bổ thông minh (Smart Allotment) và Dự báo (Forecasting).

### 2. Actor Description

| Actor name   | Description                                         |
| -------- | --------------------------------------------------------- |
| Learner Driver | Người đăng ký học, có trình độ (Level) và lịch sử học tập cụ thể |
| Instructor | Người trực tiếp hướng dẫn, có lịch làm việc và danh sách học viên phụ trách |
| AI Engine | Tác nhân hệ thống: Phân tích dữ liệu lịch sử để dự báo và tối ưu hóa việc ghép nhóm học viên |
| Admin | Người giám sát toàn bộ lịch trình và phê duyệt các điều động nhân sự dựa trên dự báo |

### 3. User Stories

-   US-01: Là một học viên, tôi muốn đặt lịch học trực tuyến để tôi có thể chủ động sắp xếp thời gian cá nhân.

-   US-02: Là một học viên, tôi muốn hệ thống gợi ý các khung giờ mà tôi có thể thực hành nhiều nhất (ít người cùng xe) hoặc cùng trình độ với các bạn khác.

-   US-03: Là một giảng viên, tôi muốn xem lịch dạy hàng tuần để chuẩn bị giáo án và xe phù hợp.

-   US-04: Là một giảng viên, tôi muốn biết trình độ của 3 học viên trong cùng một ca để có phương pháp hướng dẫn tối ưu.

-   US-05: Là một quản trị viên, tôi muốn biết dự báo số lượng học viên trong 2 tuần tới để điều động đủ số lượng giảng viên trực.

### 4. User Case Description

#### UC-01 – Book Training Session

| **Field**        | **Details** |
|------------------|-------------|
| UC ID and Name   | UC-01 – Book Training Session |
| Primary Actor    | Learner Driver |
| Secondary Actor  | AI Engine |
| Trigger          | Học viên chọn chức năng "Đặt lịch học" trên ứng dụng |
| Description      | Học viên chọn ngày, giờ và hệ thống kiểm tra tính khả dụng, đồng thời AI gợi ý slot tối ưu |
| Preconditions    | Học viên đã đăng nhập và tài khoản còn số dư buổi học hợp lệ |
| Postconditions   | Một bản ghi Booking mới được tạo, trạng thái Slot được cập nhật |
| Normal Flow      | 1. Học viên chọn ngày mong muốn<br>2. Hệ thống hiển thị danh sách khung giờ<br>3. AI Engine đánh dấu "Gợi ý tốt nhất"<br>4. Học viên chọn khung giờ<br>5. Hệ thống kiểm tra ràng buộc<br>6. Hệ thống xác nhận đặt lịch |
| Alternative Flows| A1: Đổi lịch (hủy lịch cũ trước, nếu <24h thì áp dụng phí) |
| Exceptions       | E1: Slot đã đủ 3 người<br>E2: Giảng viên gặp sự cố, session chuyển sang "Pending Re-assignment" |
| Priority         | High |
| Business Rules   | BR-01, BR-02, BR-03 |

---

#### UC-02 – Training Demand Forecasting (AI Driven)

| **Field**        | **Details** |
|------------------|-------------|
| UC ID and Name   | UC-02 – Training Demand Forecasting |
| Primary Actor    | System Admin |
| Secondary Actor  | AI Engine |
| Trigger          | Admin truy cập Dashboard báo cáo hoặc định kỳ hàng tuần |
| Description      | Hệ thống phân tích dữ liệu lịch sử để dự báo số lượng học viên và giảng viên cần thiết |
| Preconditions    | Admin có quyền truy cập Dashboard |
| Postconditions   | Biểu đồ dự báo hiển thị cho Admin |
| Normal Flow      | 1. AI Engine truy xuất dữ liệu booking lịch sử<br>2. AI tính toán số lượng ca học dự kiến<br>3. Hệ thống tính toán số lượng giảng viên cần thiết<br>4. Hệ thống hiển thị biểu đồ dự báo |
| Alternative Flows| Không có |
| Exceptions       | Không có |
| Priority         | Medium |
| Business Rules   | BR-01, BR-02, BR-03 |

### 5. Functional Requirements (FR)
-   FR-01 (Booking): Hệ thống phải cho phép học viên đặt lịch tối thiểu trước 12 giờ trước khi buổi học bắt đầu.

-   FR-02 (Allotment Control): Hệ thống phải đảm bảo không bao giờ vượt quá 3 học viên trong cùng một ca học 1 giờ.

-   FR-03 (Instructor Assignment): Hệ thống phải tự động gán giảng viên cho ca học dựa trên lịch trống và chuyên môn (xe số/xe tự động).

-   FR-04 (Smart Grouping): AI phải ưu tiên xếp các học viên có cùng tiến độ bài học (ví dụ: cùng học bài "Đề pa ngang dốc") vào cùng một ca để giảng viên tối ưu hóa việc hướng dẫn nhóm.

-   FR-05 (Forecasting Report): Hệ thống phải xuất báo cáo dự báo nhu cầu nhân sự trước mỗi kỳ Sprint/Tuần mới.

-   FR-06 (Notification): Hệ thống phải gửi thông báo (Push/Email) cho học viên và giảng viên ngay khi lịch học được xác nhận hoặc thay đổi.

### 6. Non-Functional Requirements (NFR)
-   NFR-01 (Performance): Thời gian phản hồi khi tìm kiếm slot trống phải dưới 2 giây.

-   NFR-02 (Concurrency): Hệ thống phải xử lý được ít nhất 50 yêu cầu đặt lịch đồng thời mà không gây ra tình trạng "Double Booking" (xử lý transaction ở mức database).

-   NFR-03 (Accuracy): Độ chính xác của mô hình dự báo nhu cầu AI phải đạt tối thiểu 80% sau 3 tháng tích lũy dữ liệu.

-   NFR-04 (Availability): Hệ thống booking phải hoạt động 24/7 để đáp ứng nhu cầu học viên.

### 7. Business Rules (BR)
-   BR-01 (Duration): Một ca học tiêu chuẩn kéo dài chính xác 60 phút.

-   BR-02 (Capacity): Một ca học chỉ được phép có tối đa 3 học viên tham gia.

-   BR-03 (Instructor Uniqueness): Một giảng viên không thể xuất hiện trong hai ca học có khung giờ chồng lấn nhau.

-   BR-04 (Cancellation Policy): Học viên chỉ được phép hủy lịch miễn phí trước 24 giờ. Hủy sau 24 giờ sẽ bị trừ 1 buổi học trong tài khoản.

-   BR-05 (Mandatory Association): Mọi ca học phải được liên kết với ít nhất 1 giảng viên và 1 xe tập lái cụ thể.