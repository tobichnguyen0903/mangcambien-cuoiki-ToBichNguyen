# Voice Reader điều khiển app đọc sách sử dụng kĩ thuật MFE

## Thông tin dự án

Mô hình nhận dạng lệnh giọng nói sử dụng kỹ thuật trích xuất đặc trưng MFE (Mel Filterbank Energy).

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

MFE Feature Extraction

↓

Neural Network Classifier

↓

Prediction Output
```

## Cấu trúc thư mục

```text
project-mfe/

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

### Cách 1: Chạy trực tiếp trên Edge Impulse

1. Mở Edge Impulse Studio.
2. Truy cập Deployment.
3. Chọn WebAssembly.
4. Nhấn Launch in Browser.
5. Cho phép sử dụng microphone.
6. Đọc các lệnh để kiểm tra kết quả.

### Cách 2: Chạy bộ deployment đã export

```bash
cd browser

python server.py
```

Mở trình duyệt:

```text
http://localhost:8082
```

Cho phép quyền microphone và thực hiện kiểm thử.

## Dependencies

* Edge Impulse Studio
* WebAssembly
* Python 3.x
* Google Chrome / Microsoft Edge

## Kết quả

* Accuracy: 97.5%
* Weighted F1 Score: 0.98
* Deployment: WebAssembly
