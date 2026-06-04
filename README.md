# 🛡️ HỆ THỐNG LƯU TRỮ VÀ XÁC THỰC VI PHẠM KHÔNG ĐỘI MŨ BẢO HIỂM

<div align="center">

**TRƯỜNG ĐẠI HỌC ĐẠI NAM** **KHOA CÔNG NGHỆ THÔNG TIN** **AloTLab - Faculty of Information Technology**

---

[![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)](https://www.python.org/)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-orange)](https://github.com/ultralytics/ultralytics)
[![Streamlit](https://img.shields.io/badge/Streamlit-WebApp-red?logo=streamlit)](https://streamlit.io/)
[![Blockchain](https://img.shields.io/badge/Blockchain-Ethereum-blueviolet?logo=ethereum)](https://ethereum.org/)
[![SQLite](https://img.shields.io/badge/SQLite-Database-green?logo=sqlite)](https://www.sqlite.org/)

</div>

<h3 align="center">🚦 Giải pháp phát hiện và xác thực vi phạm giao thông bằng AI và Blockchain</h3>

<p align="center">
<strong>
Hệ thống sử dụng mô hình YOLOv8 để phát hiện người điều khiển xe máy không đội mũ bảo hiểm từ hình ảnh và video. Dữ liệu vi phạm được lưu trữ bằng SQLite, tạo mã băm SHA-256 và xác thực trên Blockchain nhằm đảm bảo tính toàn vẹn, minh bạch và chống giả mạo bằng chứng vi phạm.
</strong>
</p>

---

## 📝 Giới thiệu dự án

Xác thực và bảo vệ tính toàn vẹn của ảnh vi phạm bằng công nghệ Blockchain và mã băm SHA-256. Các chức năng chính bao gồm:
* **Lưu mã băm SHA-256** của ảnh vi phạm gốc.
* **Xác thực tính toàn vẹn** dữ liệu nhanh chóng trên giao diện.
* **Phát hiện ảnh bị chỉnh sửa** hoặc có hành vi giả mạo bằng chứng.
* **Tăng tính minh bạch** và độ tin cậy tuyệt đối của bằng chứng số.

---

## 🏗️ Kiến trúc hệ thống

Hệ thống được thiết kế theo quy trình khép kín gồm 7 bước cốt lõi:

[1. Thu thập dữ liệu] ──> [2. Nhận diện vi phạm] ──> [3. Tạo bằng chứng]
(Camera / Video)            (AI YOLOv8)              (Ảnh + SHA-256)
│
▼
[5. Cảnh báo] <── [6. Dashboard] <── [7. Xác thực] <── [4. Lưu trữ]
(Telegram Bot)     (Thống kê & QL)    (Kiểm tra Hash)   (SQLite & Blockchain)


1.  **Thu nhận dữ liệu:** Tiếp nhận luồng dữ liệu hình ảnh hoặc video từ hệ thống camera giám sát.
2.  **Nhận diện vi phạm:** Sử dụng mạng neural **YOLOv8** để phân tích, phát hiện người đi xe máy không đội mũ bảo hiểm.
3.  **Tạo bằng chứng:** Trích xuất ảnh vi phạm trực quan và tự động tính toán mã băm mã hóa hình ảnh bằng thuật toán **SHA-256**.
4.  **Lưu trữ:** Đồng bộ dữ liệu hành chính vào cơ sở dữ liệu nền tảng **SQLite**, đồng thời neo giữ mã băm SHA-256 cố định lên mạng lưới **Blockchain**.
5.  **Cảnh báo:** Tự động đẩy thông tin kèm ảnh bằng chứng trực tiếp về **Telegram Bot** của lực lượng chức năng theo thời gian thực.
6.  **Dashboard:** Giao diện Web trực quan quản lý danh sách, xem chi tiết và biểu đồ thống kê vi phạm theo ngày.
7.  **Xác thực:** Module chuyên dụng cho phép tải ảnh lên để đối sánh mã hash ban đầu, kiểm tra tính vẹn toàn của bằng chứng.

---

## ✨ Tính năng chính

### 🧠 Trí tuệ nhân tạo (Computer Vision)
* Phát hiện chính xác người đội mũ bảo hiểm và không đội mũ bảo hiểm.
* Xử lý mượt mà trên cả hình ảnh tĩnh và luồng video tải lên.
* Hỗ trợ nhận diện, khoanh vùng nhiều đối tượng (Multi-object) trong cùng một khung hình với độ tin cậy ($Confidence$) cao.

### 🔐 Blockchain & Bảo mật dữ liệu
* Băm ảnh bằng chứng theo chuẩn công nghiệp **SHA-256**.
* Tương tác với Smart Contract để lưu trữ dấu vết điện tử (Proof of Existence) trên Blockchain.
* Cơ chế đối sánh mã băm hỗ trợ phát hiện ngay lập tức nếu dữ liệu ảnh bị thay đổi dù chỉ 1 pixel.

### 📊 Quản lý & Thống kê
* Quản lý danh sách vi phạm tập trung, bộ lọc tìm kiếm thông minh theo mã băm SHA-256.
* Biểu đồ cột trực quan theo dõi biến động số ca vi phạm theo các mốc thời gian trong ngày.

### 📱 Thông báo tức thời
* Bắn thông báo tự động thông qua **Telegram Bot** gồm: *Ảnh chụp vi phạm*, *Mã băm SHA-256* và *Mã hash giao dịch (TxHash)* trên Blockchain.

---

## 🔧 Công nghệ sử dụng

* **Ngôn ngữ lập trình:** Python (vế xử lý logic AI và tương tác Web3)
* **Trí tuệ nhân tạo:** Ultralytics YOLOv8, OpenCV
* **Giao diện ứng dụng:** Streamlit
* **Cơ sở dữ liệu:** SQLite
* **Nền tảng Blockchain:** Ethereum Network, Web3.py
* **Giao tiếp & Cảnh báo:** Telegram Bot API

---

## 📥 Cài đặt hệ thống

### Yêu cầu hệ thống
* Python $\ge$ 3.10
* Git

### 1. Clone dự án
```bash
git clone [https://github.com/USERNAME/helmet-detection-blockchain.git](https://github.com/USERNAME/helmet-detection-blockchain.git)
cd helmet-detection-blockchain
2. Cài đặt thư viện phụ thuộc
Bash
pip install -r requirements.txt
3. Cấu hình biến môi trường
Tạo file .env tại thư mục app/.env và thêm thông tin cấu hình Bot của bạn:

Đoạn mã
TELEGRAM_TOKEN=YOUR_BOT_TOKEN
TELEGRAM_CHAT_ID=YOUR_CHAT_ID
4. Khởi chạy Dashboard
Bash
streamlit run app/main.py
📊 Cấu trúc cơ sở dữ liệu (SQLite)
SQL
CREATE TABLE violations (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    timestamp TEXT,
    camera TEXT,
    violation_type TEXT,
    image_path TEXT,
    confidence REAL,
    image_hash TEXT,
    blockchain_tx TEXT,
    ipfs_uri TEXT
);
🔮 Hướng phát triển tương lai
Tích hợp IPFS (InterPlanetary File System): Phi tập trung hóa hoàn toàn việc lưu trữ tệp tin ảnh vi phạm gốc giúp tối ưu dung lượng và tăng tính an toàn dữ liệu.

Mở rộng hành vi vi phạm: Nâng cấp mô hình AI nhận diện thêm các hành vi vượt đèn đỏ, đi sai làn đường hoặc chở quá số người quy định.

Triển khai Public Blockchain: Chuyển đổi từ mạng thử nghiệm nội bộ sang các Public/L2 Blockchain để tăng tính minh bạch cộng đồng.

Hệ thống Edge AI: Tích hợp trực tiếp mô hình xử lý xuống các thiết bị phần cứng Camera IoT tại hiện trường thay vì xử lý tập trung trên Server.

Hệ sinh thái Smart City: Kết nối đồng bộ với mạng lưới giao thông thông minh trong mô hình đô thị hiện đại.

👨‍🎓 Thông tin tác giả & Bản quyền
Tác giả thực hiện: Hà Minh Chiến

Đơn vị: AloTLab - Khoa Công nghệ thông tin - Trường Đại học Đại Nam

Lĩnh vực nghiên cứu: AI + Blockchain + IoT + Computer Vision
