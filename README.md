# ĐỒ ÁN CUỐI KỲ MÔN HỌC MẠNG CẢM BIẾN

## Đề tài

Voice Reader điều khiển app đọc sách

---

## Sinh viên thực hiện

- Họ và tên: Tô Bích Nguyên
- MSSV: N23DCCI050
- Lớp: D23CQCI01-N

---

## Mô tả đề tài

Đề tài xây dựng hệ thống nhận dạng lệnh giọng nói bằng trí tuệ nhân tạo sử dụng nền tảng Edge Impulse.

Hệ thống được huấn luyện để nhận biết các lệnh điều khiển ứng dụng đọc sách thông qua giọng nói.

Để đánh giá hiệu quả của các phương pháp xử lý tín hiệu âm thanh, đồ án triển khai hai mô hình độc lập:

1. MFE (Mel Filterbank Energy)
2. MFCC (Mel Frequency Cepstral Coefficients)

Cả hai mô hình đều được huấn luyện bằng Neural Network và triển khai dưới dạng WebAssembly để chạy trực tiếp trên trình duyệt.

---

## Quy trình thực hiện

1. Thu thập dữ liệu âm thanh bằng microphone.
2. Gán nhãn dữ liệu trong Edge Impulse.
3. Trích xuất đặc trưng âm thanh bằng MFE hoặc MFCC.
4. Huấn luyện mô hình phân loại (Sound Classification).
5. Đánh giá mô hình bằng Accuracy, F1 Score và Confusion Matrix.
6. Triển khai mô hình bằng WebAssembly.
7. Kiểm thử trực tiếp trên trình duyệt.

---

## Công nghệ sử dụng

- Edge Impulse Studio
- Sound Classification
- Neural Network
- WebAssembly (WASM)
- JavaScript
- Python 3.x

---

## Cấu trúc thư mục

```text
mangcambien-cuoiky-ToBichNguyen/

├── dataset/
│   ├── training/
│   ├── testing/
│   ├── info.labels
│   └── README.txt
│
├── project-mfe/
│   ├── browser/
│   ├── node/
│   └── README.md
│
├── project-mfcc/
│   ├── browser/
│   ├── node/
│   └── README.md
│
└── README.md
```

---

## Giải thích thư mục

### dataset/

Chứa dữ liệu âm thanh dùng cho huấn luyện và kiểm thử mô hình.

### project-mfe/

Mô hình nhận dạng giọng nói sử dụng kỹ thuật MFE (Mel Filterbank Energy).

### project-mfcc/

Mô hình nhận dạng giọng nói sử dụng kỹ thuật MFCC (Mel Frequency Cepstral Coefficients).

### browser/

Chứa mã nguồn WebAssembly Deployment dùng để chạy mô hình trên trình duyệt.

### node/

Chứa mã nguồn Deployment dành cho môi trường Node.js.

---

## Dữ liệu sử dụng

Dữ liệu được thu trực tiếp bằng microphone trên máy tính.

Mỗi mẫu âm thanh có thời lượng khoảng 2 giây.

### Các lớp dữ liệu

- bichnguyen
- docto
- trangke
- trangtruoc
- noise

### Giải thích các nhãn dữ liệu (Labels)

| Label      | Ý nghĩa                                                |
| ---------- | ------------------------------------------------------ |
| bichnguyen | Từ khóa kích hoạt hệ thống hoặc nhận diện người dùng   |
| docto      | Lệnh yêu cầu ứng dụng đọc nội dung thành tiếng         |
| trangke    | Lệnh chuyển sang trang tiếp theo                       |
| trangtruoc | Lệnh quay lại trang trước                              |
| noise      | Tiếng ồn hoặc âm thanh không thuộc các lệnh điều khiển |

---

## Phụ thuộc (Dependencies)

### Phần mềm

- Edge Impulse Studio
- Python 3.x
- Google Chrome
- Microsoft Edge

### Phần cứng

- Máy tính có microphone
- Kết nối Internet

---

## Hướng dẫn cài đặt

### Bước 1: Clone repository

```bash
git clone https://github.com/tobichnguyen0903/mangcambien-cuoiki-ToBichNguyen.git
```

### Bước 2: Di chuyển vào thư mục dự án

```bash
cd mangcambien-cuoiky-ToBichNguyen
```

---

## Hướng dẫn chạy mô hình MFE

### Chạy trên Edge Impulse

1. Mở project MFE trên Edge Impulse Studio.
2. Chọn **Deployment**.
3. Chọn **WebAssembly**.
4. Nhấn **Launch in Browser**.
5. Cho phép sử dụng microphone.
6. Đọc các lệnh để kiểm thử.

### Chạy deployment cục bộ

```bash
cd project-mfe/browser

python server.py
```

Mở trình duyệt:

```text
http://localhost:8082
```

---

## Hướng dẫn chạy mô hình MFCC

### Chạy trên Edge Impulse

1. Mở project MFCC trên Edge Impulse Studio.
2. Chọn **Deployment**.
3. Chọn **WebAssembly**.
4. Nhấn **Launch in Browser**.
5. Cho phép sử dụng microphone.
6. Đọc các lệnh để kiểm thử.

### Chạy deployment cục bộ

```bash
cd project-mfcc/browser

python server.py
```

Mở trình duyệt:

```text
http://localhost:8082
```

---

## Các lệnh được nhận dạng

- bichnguyen
- docto
- trangke
- trangtruoc
- noise

---

## Kết quả đạt được

### Mô hình MFE

- Accuracy: 97.5%
- Weighted F1 Score: 0.98

### Mô hình MFCC

- Accuracy: 100%
- Weighted F1 Score: 1.00

---

## Liên kết dự án

### Dự án MFCC

https://studio.edgeimpulse.com/studio/1021141

### Dự án MFE

https://studio.edgeimpulse.com/studio/1018581

---

## Tài liệu tham khảo

- https://studio.edgeimpulse.com/public/162492/latest
