[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574095&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.congbt@vinuni.edu.vn
**Name:** Bui The Cong

---

## Mo ta

- Extract (Trích xuất): Thiết lập module đọc dữ liệu từ raw_data.json, tích hợp cơ chế xử lý ngoại lệ (Exception Handling) để quản lý lỗi file không tồn tại hoặc lỗi định dạng JSON.
- Validate (Kiểm chứng): Áp dụng các quy tắc kinh doanh (Business Rules) để làm sạch dữ liệu:
    - Loại bỏ các bản ghi có giá (price) nhỏ hơn hoặc bằng 0.
    - Loại bỏ các bản ghi thiếu thông tin danh mục (category).
    - Ghi lại nhật ký (Logging) số lượng bản ghi hợp lệ và bị lỗi để theo dõi sức khỏe pipeline.
- Transform (Biến đổi): Sử dụng thư viện Pandas để tối ưu hóa hiệu suất xử lý:
    - Tính toán cột discounted_price (giảm giá 10%).
    - Chuẩn hóa định dạng văn bản cho category (Title Case).
    - Thêm dấu thời gian processed_at (ISO format) để phục vụ việc kiểm toán dữ liệu (Auditing).
- Load (Lưu trữ): Xuất dữ liệu đã xử lý ra file processed_data.csv với bảng mã UTF-8 đảm bảo hiển thị đúng ký tự đặc biệt.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
- Em chạy file `generate_garbage.py` để sinh file ra file data rác garbage_data.csv.
- Sau đó chạy file `agent_simulation.py` để so sánh kết quả Agent chạy với dữ liệu sạch và dữ liệu rác
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

(Tom tat ket qua: bao nhieu records da xu ly, bao nhieu bi loai, v.v.)

Có tổng 5 records đã được xử lý, có 3 records hợp lệ được giữ lại và 2 records bị loại.