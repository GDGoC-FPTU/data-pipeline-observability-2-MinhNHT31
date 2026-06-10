[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112747&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** minhnguyenhuuthai@gmail.com
**Name:** Nguyễn Hữu Thái Minh

---

## Mo ta

Bài lab này tập trung vào việc xây dựng một hệ thống ETL Pipeline cơ bản (Extract, Validate, Transform, Load) bằng Python và Pandas. Đồng thời, bài lab còn giúp kiểm tra, đánh giá tính Observability và tầm quan trọng của Data Quality thông qua việc sử dụng mô hình AI (Agent) đưa ra các dự đoán dựa trên dữ liệu thật (Clean) và dữ liệu rác (Garbage). Thông qua đó, rút ra bài học về ảnh hưởng nghiêm trọng của dữ liệu dị biệt tới logic của AI.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
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

Tổng số bản ghi ban đầu là 5. Sau khi chạy qua bước validate, có 3 bản ghi hợp lệ được giữ lại, và 2 bản ghi bị loại (do lỗi giá trị âm hoặc category rỗng). 
Dữ liệu cuối cùng được transform (tính giảm giá 10% và chuẩn hóa category) và lưu vào `processed_data.csv` thành công.
Khi thử nghiệm Agent Simulation, agent cho phản hồi hợp lý với dữ liệu sạch nhưng lại bị đánh lừa và chọn mua 'Nuclear Reactor' với giá $999999 khi chạy trên dữ liệu rác.
