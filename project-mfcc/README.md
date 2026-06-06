# Voice Reader điều khiển app đọc sách sử dụng kĩ thuật MFCC

## Thông tin dự án

Mô hình nhận dạng lệnh giọng nói sử dụng kỹ thuật trích xuất đặc trưng MFCC (Mel Frequency Cepstral Coefficients).

## Các nhãn phân loại

* bichnguyen
* docto
* trangke
* trangtruoc
* noise

## Pipeline xử lý

```text
Audio Input

↓

MFCC Feature Extraction

↓

Neural Network Classifier

↓

Prediction Output
```

## Cấu trúc thư mục

```text
project-mfcc/

├── browser/
│   ├── edge-impulse-standalone.js
│   ├── edge-impulse-standalone.wasm
│   ├── run-impulse.js
│   ├── server.py
│   ├── index.html
│   └── README.md
│
├── node/
│   ├── edge-impulse-standalone.js
│   ├── edge-impulse-standalone.wasm
│   ├── run-impulse.js
│   └── README.md
│
└── README.md
```

## Hướng dẫn chạy

### Chạy trên Edge Impulse

1. Mở dự án MFCC trong Edge Impulse Studio.
2. Vào Deployment.
3. Chọn WebAssembly.
4. Nhấn Launch in Browser.
5. Cho phép sử dụng microphone.
6. Thực hiện kiểm thử bằng các lệnh đã huấn luyện.

### Chạy deployment cục bộ

```bash
cd browser

python server.py
```

Mở trình duyệt:

```text
http://localhost:8082
```

## Dependencies

* Edge Impulse Studio
* WebAssembly
* Python 3.x
* Google Chrome / Microsoft Edge

## Mục đích

Mô hình được xây dựng nhằm so sánh hiệu quả của kỹ thuật MFCC với MFE trong bài toán nhận dạng lệnh giọng nói.

## Kết quả

* Accuracy: 100%
* Weighted F1 Score: 1.00
* Deployment: WebAssembly
