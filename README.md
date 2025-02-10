## Giới thiệu
Dự án này sử dụng Apache JMeter để đánh giá hiệu suất của một trang web thương mại điện tử thông qua kiểm thử tải (Load Testing) và kiểm thử khả năng chịu tải (Stress Testing).

## Hướng dẫn sử dụng
### 1. Cài đặt
- Yêu cầu: 
    - Apache JMeter
    - Java 8 hoặc mới hơn.
## Cài đặt Apache JMeter
### Bước 1: Tải và cài đặt Java
JMeter yêu cầu Java để chạy. Kiểm tra phiên bản Java:
```
java -version
```
Nếu chưa có, tài và cài đặt từ trang web chính của Java: https://www.java.com

### Bước 2: Tải và cài đặt Apache JMeter
- Truy cập website của JMeter: https://jmeter.apache.org/download_jmeter.cgi
- Tải phiên bản mới nhất.
- Giải nén và chạy JMeter bằng lệnh:
```
cd apache-jmeter/bin
./jmeter.sh   # Mac/Linux
jmeter.bat    # Windows
```

# 📊 Báo Cáo Kiểm Thử Hiệu Suất Hệ Thống

## 1️⃣ Thông Tin Chung
Báo cáo này trình bày kết quả kiểm thử hiệu suất hệ thống sử dụng **Apache JMeter**. Dữ liệu thu thập bao gồm các chỉ số về **thời gian phản hồi**, **Throughput**, và **tỷ lệ lỗi**.

---

## 2️⃣ Kết Quả Phân Tích

### ⚡ Thời Gian Phản Hồi (Response Time)
- **Trung bình:** 201 ms
- **Nhỏ nhất:** 0 ms
- **Lớn nhất:** 1991 ms
- **Độ lệch chuẩn:** 226.2 ms  
> 📝 *Nhận xét:* Độ lệch chuẩn cao cho thấy sự biến động lớn trong hiệu suất. Một số yêu cầu phản hồi cực nhanh (0 ms) trong khi một số khác mất gần 2 giây.

---

### 📈 Throughput (Thông Lượng)
- **Throughput trung bình:** 0.205 requests/second  
> 📝 *Nhận xét:* Đây là mức thông lượng khá thấp. Hệ thống chỉ xử lý được khoảng **1 yêu cầu mỗi 5 giây**, không đáp ứng tốt với khối lượng lớn yêu cầu đồng thời.

---

### ❌ Tỷ Lệ Lỗi (Error Rate)
- **Tỷ lệ lỗi trung bình:** 33.33%  
> 📝 *Nhận xét:* Tỷ lệ lỗi cao bất thường. Thông thường, một hệ thống ổn định sẽ có tỷ lệ lỗi dưới 1%.

---

## 3️⃣ Kết Luận

- Hệ thống **hiệu suất kém**, chưa đáp ứng tốt với khối lượng yêu cầu.
- **Thời gian phản hồi không ổn định**, dao động lớn từ 0 đến gần 2 giây.
- **Throughput thấp**, không phù hợp cho các hệ thống yêu cầu xử lý nhanh và đồng thời cao.
- **Tỷ lệ lỗi cao**, có thể do giới hạn tài nguyên hoặc lỗi từ ứng dụng.

---
# 📊 Báo Cáo Kiểm Thử Tải (Load Testing)

## 1️⃣ Thông Tin Chung
Báo cáo này trình bày kết quả kiểm thử hiệu suất hệ thống sử dụng **Apache JMeter** với các mức tải khác nhau: **10, 30 và 50 người dùng đồng thời**. Các chỉ số được phân tích gồm **thời gian phản hồi (Response Time)**, **Throughput**, và **tỷ lệ lỗi (Error Rate)**.

---

## 2️⃣ Kết Quả So Sánh

| **Chỉ Số**                        | **Tải 10**         | **Tải 30**         | **Tải 50**         |
|:----------------------------------|:------------------:|:------------------:|:------------------:|
| ⏱️ **Thời gian phản hồi TB (ms)** | 218               | 228               | 247               |
| 🚀 **Throughput (requests/sec)**  | 0.254             | 0.273             | 0.310             |
| ❌ **Tỷ lệ lỗi (%)**              | 19.23%            | 17.24%            | 14.71%            |
| 📉 **Thời gian phản hồi nhỏ nhất (ms)** | 0                 | 0                 | 0                 |
| 📈 **Thời gian phản hồi lớn nhất (ms)** | 1991              | 1991              | 1991              |
| 🔀 **Độ lệch chuẩn (ms)**         | 182.49            | 178.45            | 179.21            |

---

## 3️⃣ Phân Tích Chi Tiết

### ⏱️ **Thời Gian Phản Hồi (Response Time)**
- **Xu hướng:** Tăng dần khi tải tăng (từ 218 ms lên 247 ms).
- **Nhận xét:** Hệ thống phản hồi chậm hơn khi số lượng người dùng tăng, tuy nhiên sự gia tăng không quá đột biến.

---

### 🚀 **Throughput (Thông Lượng)**
- **Xu hướng:** Tăng từ 0.254 lên 0.310 requests/second khi tải tăng.
- **Nhận xét:** Throughput cải thiện dần khi tải tăng, cho thấy hệ thống có khả năng xử lý đồng thời tốt hơn ở mức tải cao hơn.

---

### ❌ **Tỷ Lệ Lỗi (Error Rate)**
- **Xu hướng:** Giảm từ 19.23% xuống còn 14.71% khi tải tăng.
- **Nhận xét:** Đây là kết quả bất ngờ, có thể do hệ thống tối ưu tốt hơn ở các mức tải lớn hoặc do các yếu tố không ổn định ở mức tải thấp.

---

## 4️⃣ Kết Luận

- **Hiệu suất hệ thống có xu hướng ổn định** khi tải tăng, với Throughput tăng và tỷ lệ lỗi giảm.
- **Thời gian phản hồi tăng nhẹ**, nhưng không gây ảnh hưởng lớn đến trải nghiệm người dùng trong phạm vi thử nghiệm.
- **Tỷ lệ lỗi vẫn ở mức cao (trên 14%)**, cần được phân tích sâu hơn để xác định nguyên nhân.

---
# 📊 Báo Cáo Kiểm Thử Khả Năng Chịu Tải (Stress Testing)

## 1️⃣ Thông Tin Chung
Báo cáo này trình bày kết quả kiểm thử hiệu suất hệ thống sử dụng **Apache JMeter** trong điều kiện chịu tải. Các chỉ số quan trọng được phân tích gồm **thời gian phản hồi (Response Time)**, **Throughput**, và **tỷ lệ lỗi (Error Rate)**.

---

## 2️⃣ Kết Quả Phân Tích

| **Chỉ Số**                        | **Giá Trị**         |
|:----------------------------------|:-------------------:|
| ⏱️ **Thời gian phản hồi TB (ms)** | 215                |
| 📉 **Thời gian phản hồi nhỏ nhất (ms)** | 0                  |
| 📈 **Thời gian phản hồi lớn nhất (ms)** | 1991               |
| 🔀 **Độ lệch chuẩn (ms)**         | 183.59             |
| 🚀 **Throughput (requests/sec)**  | 0.279              |
| ❌ **Tỷ lệ lỗi (%)**              | 20.00%             |

---

## 3️⃣ Phân Tích Chi Tiết

### ⏱️ **Thời Gian Phản Hồi (Response Time)**
- **Trung bình:** 215 ms  
- **Biến động:** Độ lệch chuẩn cao (183.59 ms) cho thấy sự không ổn định, với các phản hồi dao động từ **0 ms** đến gần **2 giây (1991 ms)**.
- **Nhận xét:** Thời gian phản hồi không ổn định có thể gây ảnh hưởng đến trải nghiệm người dùng, đặc biệt trong các tình huống yêu cầu phản hồi nhanh.

---

### 🚀 **Throughput (Thông Lượng)**
- **Throughput trung bình:** 0.279 requests/second (~1 yêu cầu mỗi 3.58 giây).
- **Nhận xét:** Thông lượng ở mức thấp đối với các hệ thống cần xử lý đồng thời cao. Điều này có thể do giới hạn tài nguyên hệ thống hoặc tắc nghẽn mạng.

---

### ❌ **Tỷ Lệ Lỗi (Error Rate)**
- **Tỷ lệ lỗi:** 20% (rất cao so với tiêu chuẩn thông thường, thường dưới 1% với hệ thống ổn định).
- **Nhận xét:** Tỷ lệ lỗi cao chỉ ra các vấn đề nghiêm trọng trong xử lý yêu cầu, có thể do lỗi ứng dụng hoặc giới hạn hiệu năng hệ thống.

---

## 4️⃣ Kết Luận

- **Hiệu suất hệ thống chưa đạt yêu cầu:**  
  - **Thời gian phản hồi không ổn định**, với độ lệch chuẩn cao.  
  - **Throughput thấp**, không đáp ứng tốt khi hệ thống chịu tải lớn.  
  - **Tỷ lệ lỗi cao**, cho thấy hệ thống gặp khó khăn khi xử lý khối lượng yêu cầu lớn.

---
# Tài liệu tham khảo
https://chatgpt.com/share/67a98740-0c00-8002-b6dd-4a3c6ac44486

---

# Câu hỏi thảo luận

## 1. Tại sao kiểm thử phi chức năng lại quan trọng trong phần mềm?

Kiểm thử phi chức năng (Non-Functional Testing - NFT) giúp đảm bảo phần mềm không chỉ **hoạt động đúng** mà còn **hiệu quả**, **ổn định**, và **bền vững** trong môi trường thực tế.  

### 🎯 **Lý do quan trọng:**
- **Hiệu suất (Performance):** Đo lường tốc độ và độ ổn định khi hệ thống chịu tải nặng.
- **Trải nghiệm người dùng (User Experience):** Đảm bảo phần mềm nhanh chóng, mượt mà và dễ sử dụng.
- **Độ tin cậy (Reliability):** Hệ thống hoạt động ổn định trong thời gian dài.
- **Bảo mật (Security):** Kiểm tra các lỗ hổng bảo mật để bảo vệ dữ liệu.
- **Khả năng mở rộng (Scalability):** Đánh giá hệ thống có thể xử lý tốt khi số lượng người dùng tăng lên.
- **Tuân thủ (Compliance):** Đáp ứng các tiêu chuẩn và quy định pháp lý (GDPR, ISO, v.v).

---

## 2. Các thông số quan trọng trong kiểm thử hiệu suất

Khi thực hiện kiểm thử hiệu suất (Performance Testing), cần theo dõi các thông số sau:  

### 📊 **Thông số chính:**
- **Throughput (Thông lượng):** Số lượng yêu cầu xử lý mỗi giây (requests/second).
- **Response Time (Thời gian phản hồi):**
  - **Average Response Time:** Thời gian phản hồi trung bình.
  - **90th/95th Percentile:** 90% hoặc 95% yêu cầu có thời gian phản hồi dưới mức này.
- **Latency (Độ trễ):** Thời gian chờ giữa lúc gửi yêu cầu và nhận phản hồi đầu tiên.
- **Error Rate (Tỷ lệ lỗi):** Tỷ lệ phần trăm các yêu cầu thất bại.
- **CPU & Memory Utilization (Sử dụng CPU/RAM):** Đo mức tiêu thụ tài nguyên hệ thống.
- **Concurrency Level (Mức độ đồng thời):** Số lượng người dùng hoặc yêu cầu đồng thời mà hệ thống có thể xử lý.
- **Bandwidth (Băng thông):** Tốc độ truyền tải dữ liệu giữa máy chủ và máy khách.

---

## 3. Giải pháp khi hệ thống không đáp ứng yêu cầu hiệu suất

Khi phát hiện hệ thống kém hiệu suất, cần thực hiện các bước sau để tối ưu:

### 🔍 **1. Phân tích và tối ưu hóa ứng dụng**
- **Tối ưu mã nguồn:** Cải thiện thuật toán, tối ưu hóa code.
- **Tối ưu truy vấn cơ sở dữ liệu:** Giảm độ phức tạp của SQL, sử dụng indexing hiệu quả.
- **Caching:** Áp dụng Redis, Memcached để giảm tải cho hệ thống backend.

### ⚡ **2. Cải thiện cơ sở hạ tầng**
- **Load Balancing:** Phân phối đều tải lên nhiều máy chủ để tránh bottleneck.
- **Tăng tài nguyên phần cứng:** Thêm CPU, RAM hoặc nâng cấp phần cứng hiện có.
- **Scaling:**
  - **Vertical Scaling:** Tăng cường năng lực máy chủ hiện tại (CPU/RAM mạnh hơn).
  - **Horizontal Scaling:** Thêm nhiều máy chủ để xử lý song song.

### 🚀 **3. Tối ưu hóa hệ thống backend**
- **Database Tuning:** Tối ưu cấu trúc bảng, indexing và tối ưu các câu truy vấn phức tạp.
- **Asynchronous Processing:** Xử lý các tác vụ nặng ở chế độ không đồng bộ để giảm tải cho hệ thống chính.
- **Queue Systems:** Sử dụng hệ thống hàng đợi như **RabbitMQ**, **Kafka** để xử lý dữ liệu lớn hiệu quả hơn.

### 📈 **4. Kiểm thử lại và giám sát hệ thống**
- **Kiểm thử lại:** Chạy lại các bài kiểm thử hiệu suất sau khi tối ưu để đánh giá sự cải thiện.
- **Giám sát (Monitoring):** Sử dụng các công cụ như **Prometheus**, **Grafana** để theo dõi hiệu suất hệ thống theo thời gian thực.

---

## 📌 **Kết luận**

Kiểm thử phi chức năng là một phần không thể thiếu để đảm bảo phần mềm không chỉ **chạy đúng**, mà còn phải **chạy tốt** trong mọi điều kiện. Việc liên tục theo dõi và tối ưu hiệu suất sẽ giúp hệ thống đạt được:  
- **Hiệu quả cao hơn**  
- **Trải nghiệm người dùng tốt hơn**  
- **Khả năng mở rộng và bảo mật tối ưu**  

---



