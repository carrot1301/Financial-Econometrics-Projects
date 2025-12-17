# Định Lượng Rủi Ro Vĩ Mô & Đánh Giá Giới Hạn Mô Hình

## 📌 Tổng quan dự án
Dự án này áp dụng các phương pháp kinh tế lượng tài chính (Financial Econometrics) để định lượng độ nhạy cảm của tài sản tài chính đối với các yếu tố kinh tế vĩ mô. Dựa trên khung lý thuyết **Futures Platform Macro Risk Radar**, bài phân tích tập trung vào mối quan hệ giữa **Giá Dầu thô (Yếu tố vĩ mô)** và **Quỹ ETF Ngành Năng lượng - XLE (Tài sản rủi ro)**.

Mục tiêu chính là xây dựng mô hình hồi quy tuyến tính để đo lường rủi ro hệ thống và kiểm định các giả định thống kê quan trọng của mô hình.

## 🛠 Công cụ & Kỹ thuật sử dụng
* **Ngôn ngữ:** Python 3.x
* **Môi trường:** Google Colab (Jupyter Notebook)
* **Thư viện chính:**
    * `yfinance`: Thu thập dữ liệu thị trường lịch sử.
    * `pandas` & `numpy`: Xử lý, làm sạch và biến đổi dữ liệu chuỗi thời gian.
    * `statsmodels`: Thực hiện kiểm định ADF (tính dừng) và chạy mô hình hồi quy OLS.
    * `seaborn` & `matplotlib`: Trực quan hóa dữ liệu và phân tích phần dư.

## 📊 Các bước phân tích chính
1.  **Thu thập dữ liệu:** Tải dữ liệu giá điều chỉnh (Adjusted Close) trong 5 năm từ Yahoo Finance API.
2.  **Chuyển đổi dữ liệu:** Chuyển từ chuỗi giá (Prices) sang chuỗi lợi suất Log (Log Returns) để đảm bảo tính dừng (Stationarity).
3.  **Thống kê mô tả:** Phân tích các chỉ số Mean, Volatility, Skewness, Kurtosis để đánh giá rủi ro đuôi (Fat-tail risk).
4.  **Kiểm định tính dừng (Stationarity Test):** Sử dụng kiểm định **Augmented Dickey-Fuller (ADF)** để xác nhận dữ liệu phù hợp cho mô hình hồi quy ($p < 0.05$).
5.  **Mô hình hóa:** Xây dựng mô hình Hồi quy Tuyến tính Đơn (Simple Linear Regression - OLS) để tìm hệ số Beta ($\beta$).
6.  **Đánh giá giả định:** Kiểm tra tính đồng nhất của phương sai sai số (Homoscedasticity) thông qua đồ thị phần dư (Residual Plot).

## 📈 Kết quả nổi bật
* **Tương quan (Correlation):** Tìm thấy mối tương quan dương mạnh mẽ giữa biến động giá Dầu và cổ phiếu ngành Năng lượng.
* **Độ nhạy (Sensitivity):** Kết quả mô hình OLS cho thấy với mỗi **1%** thay đổi của giá Dầu, ETF Năng lượng dự kiến thay đổi khoảng **[Điền số Beta của bạn vào đây, ví dụ: 0.54]%**.
* **Độ tin cậy ($R^2$):** Mô hình giải thích được khoảng **[Điền R2, ví dụ: 45]%** sự biến động của giá cổ phiếu năng lượng.
* **Giới hạn:** Phân tích phần dư cho thấy sự hiện diện của hiện tượng phương sai thay đổi (Heteroscedasticity) trong các giai đoạn thị trường biến động mạnh, gợi ý cần sử dụng các mô hình nâng cao hơn như GARCH.

## ⚠️ Tuyên bố miễn trừ trách nhiệm
Dự án này chỉ phục vụ mục đích nghiên cứu và học tập, không được xem là lời khuyên đầu tư tài chính.

---
**Tác giả:** Đoàn Nguyên Trí
**Liên hệ:** doantri12343@gmail.com
