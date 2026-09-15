# 📊 Ứng Dụng Cấp Số Nhân Trong Bài Toán Tài Chính Và Lãi Kép

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)

Dự án này cung cấp các công cụ mã nguồn, tài liệu hướng dẫn và các ví dụ trực quan về cách ứng dụng lý thuyết **cấp số nhân (Geometric Progression)** vào việc phân tích và giải quyết các bài toán thực tế trong lĩnh vực **tài chính** và **lãi kép (Compound Interest)**.

---

## 📑 Mục lục
- [Giới thiệu](#-giới-thiệu)
- [Cơ sở lý thuyết](#-cơ-sở-lý-thuyết)
  - [1. Cấp số nhân](#1-cấp-số-nhân)
  - [2. Lãi kép](#2-lãi-kép)
  - [3. Dòng tiền đều (Annuity)](#3-dòng-tiền-đều-annuity)
- [Cấu trúc thư mục](#-cấu-trúc-thư-mục)
- [Cài đặt & Sử dụng](#-cài-đặt--sử-dụng)
- [Các tính năng chính](#-các-tính-năng-chính)
- [Đóng góp](#-đóng-góp)
- [Giấy phép](#-giấy-phép)

---

## 💡 Giới thiệu

Nhiều người cho rằng toán học cao cấp ít có ứng dụng trong đời sống thực tế, nhưng **cấp số nhân** lại là một trong những công cụ mạnh mẽ nhất chi phối sự tăng trưởng của tiền tệ. Dự án này được tạo ra nhằm mục đích:
1. **Giáo dục:** Giúp sinh viên và những người quan tâm hiểu rõ bản chất toán học đằng sau các công thức tài chính.
2. **Thực hành:** Cung cấp các đoạn mã Python để tự động hóa việc tính toán lãi suất tiết kiệm, định giá các khoản vay trả góp và lập kế hoạch hưu trí.

---

## 📐 Cơ sở lý thuyết

### 1. Cấp số nhân
Cấp số nhân là một dãy số trong đó tỷ số giữa hai số hạng liên tiếp luôn là một hằng số (gọi là công bội $q$).
- Số hạng tổng quát: $u_n = u_1 	imes q^{n-1}$
- Tổng $n$ số hạng đầu tiên: $S_n = u_1 	imes rac{1 - q^n}{1 - q} $ (với $q 
eq 1$)

### 2. Lãi kép
Lãi kép chính là một ứng dụng trực tiếp của cấp số nhân. Nếu bạn gửi số tiền ban đầu (Principal) là $P$, với lãi suất $r$/năm. Sau $n$ năm, tổng số tiền nhận được (Future Value - FV) tạo thành một cấp số nhân với công bội $q = (1 + r)$:
- **Công thức:** $FV = P 	imes (1 + r)^n$

### 3. Dòng tiền đều (Annuity)
Nếu mỗi năm bạn đều đặn gửi vào ngân hàng một số tiền là $A$ với lãi suất $r$/năm. Sau $n$ năm, tổng số tiền bạn có chính là tổng của một cấp số nhân:
- **Công thức:** $FV = A 	imes rac{(1 + r)^n - 1}{r}$

---

## 📂 Cấu trúc thư mục

```text
financial-geometric-progression/
│
├── src/                    # Chứa mã nguồn Python chính
│   ├── compound_interest.py # Hàm tính toán lãi kép cơ bản
│   ├── annuity.py           # Hàm tính toán giá trị dòng tiền đều
│   └── loan_amortization.py # Bảng tính trả góp khoản vay
│
├── docs/                   # Tài liệu chứng minh công thức (PDF/Markdown)
│
├── examples/               # Các Jupyter Notebooks chứa ví dụ minh họa
│   └── investment_case_study.ipynb
│
├── tests/                  # Unit tests đảm bảo tính chính xác của các hàm
│
├── requirements.txt        # Các thư viện phụ thuộc (vd: pandas, matplotlib)
└── README.md               # File thông tin dự án
```

---

## 🚀 Cài đặt & Sử dụng

**1. Clone kho lưu trữ:**
```bash
git clone https://github.com/yourusername/financial-geometric-progression.git
cd financial-geometric-progression
```

**2. Tạo môi trường ảo và cài đặt thư viện:**
```bash
python -m venv venv
source venv/bin/activate  # (Trên Windows dùng: venv\Scripts\activate)
pip install -r requirements.txt
```

**3. Chạy ví dụ cơ bản trong Python:**
```python
from src.compound_interest import calculate_fv

# Gửi 100,000,000 VND, lãi suất 7%/năm, trong 10 năm
fv = calculate_fv(principal=100000000, rate=0.07, years=10)
print(f"Tổng số tiền sau 10 năm: {fv:,.0f} VND")
```

---

## 🎯 Các tính năng chính

- **Tính toán linh hoạt:** Hỗ trợ kỳ hạn ghép lãi linh hoạt (hàng năm, hàng tháng, hàng ngày).
- **Vẽ biểu đồ trực quan:** Tích hợp `matplotlib` để hiển thị sự tăng trưởng của dòng tiền theo dạng hàm mũ (đặc trưng của lãi kép).
- **Lập lịch trả nợ (Amortization Schedule):** Áp dụng cấp số nhân để tách bạch phần lãi và phần gốc trong mỗi kỳ trả góp ngân hàng.
- **Phân tích hưu trí:** Tính toán số tiền cần tiết kiệm mỗi tháng để đạt được mục tiêu tự do tài chính.

---

## 🤝 Đóng góp

Chúng tôi hoan nghênh mọi đóng góp để hoàn thiện dự án! Nếu bạn có ý tưởng cải tiến hoặc tìm thấy lỗi, vui lòng:
1. Fork dự án này.
2. Tạo một nhánh mới (`git checkout -b feature/AmazingFeature`).
3. Commit các thay đổi của bạn (`git commit -m 'Add some AmazingFeature'`).
4. Push lên nhánh đó (`git push origin feature/AmazingFeature`).
5. Mở một Pull Request.

---

## 📜 Giấy phép

Dự án này được phân phối dưới giấy phép MIT. Xem file `LICENSE` để biết thêm thông tin chi tiết.

---
*Tác giả: Minh Quang - 2026*
