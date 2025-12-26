\# 🌤️ Vietnam Weather Analysis \& Prediction Project



\## Group Information (Group 14)

| Student ID | Full Name | Role |

| :--- | :--- | :--- |

| \*\*23127408\*\* | \*\*Nguyễn Thành Lợi\*\* | Data Analysis, Visualization |

| \*\*22127330\*\* | \*\*Nguyễn Đức Phúc\*\* | Modeling, Feature Engineering, API Integration |



---



\## Project Overview

Dự án này tập trung phân tích dữ liệu thời tiết tại Việt Nam (giai đoạn 2024-2025) nhằm mục đích:

1\.  \*\*Xây dựng mô hình Machine Learning\*\* để dự báo Nhiệt độ và Lượng mưa.

2\.  \*\*Khám phá Insight\*\* phục vụ cho Năng lượng tái tạo (Điện gió/Mặt trời) và Du lịch.

3\.  \*\*Thử nghiệm thực tế\*\* khả năng dự báo bão thông qua tích hợp API thời gian thực.



---



\## 📂 Project Structure

Dự án được tổ chức theo quy trình Data Science tiêu chuẩn:



```text

├── data/                          # Thư mục chứa dữ liệu

│   ├── weather\_raw.csv            # Dữ liệu gốc

│   └── weather\_preprocessed.csv   # Dữ liệu sau khi làm sạch \& Feature Engineering

├── notebooks/                     # Mã nguồn Jupyter Notebook

│   ├── 01\_Exploration\_Preprocessing.ipynb  # EDA, xử lý NaN, tạo Lag Features

│   ├── 02\_Modeling\_Prediction.ipynb        # Train model, Evaluate, API Forecast

│   └── 03\_Meaningful\_Questions.ipynb       # Phân tích Năng lượng \& Du lịch

└── README.md                      # Tài liệu dự án



\# Methodology \& Pipeline



\## 1. Data Preprocessing \& Feature Engineering



\- \*\*Handling Missing Values\*\*  

&nbsp; Xử lý dữ liệu khuyết thiếu.



\- \*\*Cyclical Encoding\*\*  

&nbsp; Chuyển đổi dữ liệu thời gian (Ngày, Tháng) sang dạng Sin/Cos để giữ tính chu kỳ.



\- \*\*Geospatial \& Terrain\*\*  

&nbsp; Sử dụng One-Hot Encoding cho đặc trưng địa hình (Terrain) và tọa độ (Lat/Lon).



\- \*\*Lag Features (Quan trọng)\*\*  

&nbsp; Tạo các biến trễ (dữ liệu của ngày hôm qua `prev\_1d\_...`) để phục vụ bài toán dự báo (Forecasting).



---



\## 2. Modeling Strategy



Chúng tôi tiếp cận theo \*\*hai hướng\*\*:



\- \*\*Diagnostic Model\*\*  

&nbsp; Dùng các chỉ số hiện tại (UV, Cloud Cover, Wind) để chẩn đoán lượng mưa.



\- \*\*Forecasting Model\*\*  

&nbsp; Dùng dữ liệu quá khứ (Lag Features) để dự báo ngày tiếp theo.



\### Các thuật toán sử dụng



\- Linear Regression (Baseline)  

\- Random Forest Regressor 🏆  

\- Gradient Boosting / XGBoost / LightGBM  

\- MLP Regressor (Neural Network cơ bản)



---



\# 📊 Key Results



\## 1. Hiệu năng Mô hình (Model Performance)



| Target Variable | Best Model         | R² Score | MAE    | Insight |

|----------------|-------------------|----------|--------|---------|

| Nhiệt độ (Max Temp) | Gradient Boosting | ~0.88 | 1.2°C | Mô hình dự báo nhiệt độ rất chính xác nhờ vào tính ổn định của chuỗi thời gian nhiệt. |

| Lượng mưa (Rainfall) | Random Forest | ~0.42 | 4.2 mm | Dự báo mưa khó khăn hơn do tính ngẫu nhiên cao. Tuy nhiên, mô hình bắt tốt xu hướng mưa/không mưa. |



---



\## 2. Nghiên cứu Thực tiễn (Case Studies)



\### ☀️ Question 1: Tiềm năng Năng lượng Tái tạo



\- \*\*Điện mặt trời\*\*  

&nbsp; Khu vực Đông Nam Bộ là tối ưu nhất với chỉ số bức xạ cao và ổn định quanh năm.  

&nbsp; Miền Bắc bị hạn chế vào mùa Đông/Xuân.



\- \*\*Điện gió\*\*  

&nbsp; Vùng Duyên hải Nam Trung Bộ \& Tây Nguyên có tiềm năng gió lớn nhất, thích hợp cho các Wind Farms quy mô lớn.



---



\### ✈️ Question 2: Tối ưu hóa Du lịch (Comfort Index)



\- Xây dựng chỉ số \*\*Comfort Index\*\* dựa trên:

&nbsp; - Nhiệt độ: 20–28°C  

&nbsp; - Độ ẩm: < 85%  

&nbsp; - Mưa: < 5 mm  



\- \*\*Kết luận\*\*  

&nbsp; Tháng 11 và Tháng 12 là \*\*"Thời điểm vàng"\*\* để du lịch xuyên Việt với xác suất thời tiết đẹp cao nhất trên cả 3 miền.



---



\## 🚀 Advanced Feature: Real-time Storm Tracking



Dự án đã tích hợp thành công \*\*Open-Meteo API\*\* để kiểm chứng mô hình với dữ liệu thực tế:



\- \*\*Khả năng\*\*

&nbsp; - Tự động lấy dữ liệu thời tiết hiện tại theo tọa độ (Lat/Lon)



\- \*\*Kiểm chứng\*\*

&nbsp; - Đã test trên các cơn bão lịch sử năm 2025 (Yagi, Trà Mi, Bão số 15)



\- \*\*Kết quả\*\*

&nbsp; - Mô hình Random Forest có khả năng cảnh báo sớm các đợt mưa lớn với độ chính xác tương đối về xu hướng.



---



\## 🔮 Future Directions



Nếu có thêm thời gian và tài nguyên, nhóm sẽ phát triển theo hướng:



\- \*\*Deep Learning\*\*  

&nbsp; Áp dụng LSTM/GRU để mô hình hóa chuỗi thời gian dài hạn tốt hơn.



\- \*\*Satellite Data\*\*  

&nbsp; Tích hợp ảnh vệ tinh để theo dõi độ phủ mây (Cloud cover) theo thời gian thực.



\- \*\*Radar\*\*  

&nbsp; Sử dụng dữ liệu Radar để dự báo mưa cực ngắn (Nowcasting).



