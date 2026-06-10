# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600619
**Name:** Nguyễn Hữu Thái Minh
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Hợp lý, dữ liệu chính xác và thực tế. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Sai hoàn toàn, do dữ liệu dị biệt (outlier) làm hỏng logic. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi sử dụng dữ liệu rác (Garbage Data) cho Agent, có thể thấy kết quả trả về hoàn toàn sai lệch và phi lý, cụ thể ở đây là Agent gợi ý mua 'Nuclear Reactor' (Lò phản ứng hạt nhân) với giá lên đến 999,999 USD. Nguyên nhân chính là do tập dữ liệu rác chứa những điểm dữ liệu dị biệt (Extreme Outliers) có giá trị quá lớn so với thực tế, làm hỏng hoàn toàn logic đơn giản của Agent là tìm kiếm sản phẩm điện tử có giá cao nhất để gợi ý. Bên cạnh đó, tập dữ liệu rác thường còn chứa các vấn đề nghiêm trọng khác như trùng lặp định danh (Duplicate IDs), sai kiểu dữ liệu (chữ số thập phân bị ghi thành chữ viết tay), hoặc các trường quan trọng bị bỏ trống (Null values). Những lỗi này không chỉ làm giảm chất lượng phản hồi, làm mất độ tin cậy của AI, mà trong một số trường hợp thực tế còn có thể gây lỗi hệ thống (exception), làm cho toàn bộ ứng dụng bị sập trong lúc thực thi.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý.

Cho dù prompt (câu lệnh) có tốt và tối ưu đến đâu, nếu dữ liệu truyền vào là dữ liệu rác (garbage in), thì kết quả mà AI đưa ra chắc chắn cũng sẽ sai lệch và thiếu tin cậy (garbage out). Dữ liệu sạch là nền tảng cốt lõi và quan trọng nhất để xây dựng bất kỳ một mô hình AI hay hệ thống Pipeline nào.
