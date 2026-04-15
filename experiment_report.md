# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-0008
**Name:** Bùi Thế Công
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 10 | |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 3 | |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi dùng `garbage_data.csv`, dữ liệu chứa nhiều vấn đề chất lượng rõ ràng. Có duplicate ID (hai bản ghi cùng `id=1`), một giá trị `price` không phải số (`ten dollars`), một bản ghi thiếu `id` và thiếu `category`, và một giá trị outlier cực đoan (`999999`) cho sản phẩm không phù hợp. Những lỗi này khiến agent không thể đánh giá đúng quy mô, tính hợp lệ và so sánh giá trị giữa các sản phẩm. Cụ thể, giá trị kiểu sai và thiếu dữ liệu phá vỡ bước xử lý tiền xử lý, trong khi outlier làm sai lệch lựa chọn “best choice” thành Nuclear Reactor bất hợp lý. Vì vậy dù prompt có tốt, agent vẫn trả lời sai do dữ liệu thô đã bị nhiễu.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Đồng ý. Dữ liệu chất lượng tốt là điều kiện tiên quyết. Prompt có thể giúp định hướng, nhưng nếu dữ liệu đầu vào bị sai, thiếu hoặc nhiễu, kết quả của agent vẫn sẽ sai lệch.
