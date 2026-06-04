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

Dự án tập trung vào việc xác thực và bảo vệ tính toàn vẹn của ảnh vi phạm bằng công nghệ Blockchain kết hợp mã băm SHA-256. Các chức năng cốt lõi bao gồm:
* **Lưu mã băm SHA-256** của ảnh vi phạm gốc để tạo dấu vết số cố định.
* **Xác thực tính toàn vẹn** dữ liệu nhanh chóng và trực quan ngay trên giao diện Web.
* **Phát hiện ảnh bị chỉnh sửa** hoặc các hành vi làm sai lệch, giả mạo bằng chứng.
* **Nâng cao tính minh bạch** và độ tin cậy tuyệt đối cho quy trình xử lý vi phạm giao thông.

---

## 🏗️ Kiến trúc hệ thống

Quy trình vận hành của hệ thống bao gồm 7 bước khép kín từ khâu thu thập dữ liệu hiện trường cho đến bước xác thực cuối cùng:

<p align="center">
  <img src="Porter.png" alt="Kiến trúc hệ thống và Giao diện" width="750"/>
</p>

1. **Thu thập dữ liệu:** Tiếp nhận luồng dữ liệu hình ảnh hoặc video từ hệ thống camera giám sát giao thông.
2. **Nhận diện vi phạm:** Sử dụng mạng trí tuệ nhân tạo (AI YOLOv8) phân tích, phát hiện người đi xe máy không đội mũ bảo hiểm.
3. **Tạo bằng chứng:** Trích xuất ảnh vi phạm trực quan và tự động tính toán mã băm định danh bằng thuật toán **SHA-256**.
4. **Lưu trữ:** Đồng bộ dữ liệu hành chính vào cơ sở dữ liệu **SQLite**, đồng thời neo giữ mã băm SHA-256 cố định lên mạng lưới **Blockchain Ethereum**.
5. **Cảnh báo:** Tự động đẩy thông tin và ảnh bằng chứng trực tiếp về ứng dụng **Telegram Bot** của lực lượng chức năng.
6. **Dashboard:** Giao diện Web trực quan hiển thị danh sách vi phạm, xem chi tiết ảnh chụp và thống kê số liệu quản lý.
7. **Xác thực:** Module đối sánh mã hash giúp kiểm tra tính vẹn toàn, phát hiện ngay nếu bằng chứng bị can thiệp.

---

## ✨ Tính năng chính

### 🧠 Trí tuệ nhân tạo (Computer Vision)
* Phát hiện chính xác người đội mũ bảo hiểm và không đội mũ bảo hiểm.
* Xử lý mượt mà trên cả hình ảnh tĩnh và luồng video tải lên.
* Hỗ trợ nhận diện, khoanh vùng nhiều đối tượng (Multi-object) cùng lúc với độ tin cậy ($Confidence$) cao.

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

* **Ngôn ngữ lập trình:** Python (xử lý logic AI, Backend và tương tác Web3)
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
Tạo file .env tại thư mục app/.env và điền thông tin cấu hình Bot của bạn:

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

💡 Việc bạn cần làm bây giờ:
Sao chép toàn bộ khối mã Markdown ở trên.

Mở file README.md trong IDE (như VS Code) của bạn ra, xóa sạch nội dung cũ đi và dán nội dung này vào.

Lưu file lại (Ctrl + S), lúc này mã nguồn đã gọi trực tiếp ảnh Porter.png (đúng viết hoa chữ P) nên sơ đồ và poster của bạn sẽ lập tức hiển thị sắc nét trên giao diện!
