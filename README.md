🌤️ Vietnam Weather Analysis & Prediction Project
Group Information (Group 14)
Student ID	Full Name	Role
23127408	Nguyễn Thành Lợi	Data Analysis, Visualization
22127330	Nguyễn Đức Phúc	Modeling, Feature Engineering, API Integration
Project Overview

Dự án này tập trung phân tích dữ liệu thời tiết tại Việt Nam (giai đoạn 2024–2025) nhằm mục đích:

Xây dựng mô hình Machine Learning để dự báo Nhiệt độ và Lượng mưa

Khám phá insight phục vụ cho Năng lượng tái tạo (Điện gió / Mặt trời) và Du lịch

Thử nghiệm thực tế khả năng dự báo bão thông qua tích hợp API thời gian thực

📂 Project Structure

Dự án được tổ chức theo quy trình Data Science tiêu chuẩn:

├── data/
│   ├── weather_raw.csv
│   └── weather_preprocessed.csv
│
├── notebooks/
│   ├── 01_Exploration_Preprocessing.ipynb
│   ├── 02_Modeling_Prediction.ipynb
│   └── 03_Meaningful_Questions.ipynb
│
└── README.md

Methodology & Pipeline
1. Data Preprocessing & Feature Engineering

Handling Missing Values
Xử lý dữ liệu khuyết thiếu.

Cyclical Encoding
Chuyển đổi dữ liệu thời gian (Ngày, Tháng) sang dạng Sin / Cos để giữ tính chu kỳ.

Geospatial & Terrain
Sử dụng One-Hot Encoding cho đặc trưng địa hình (Terrain) và tọa độ (Lat / Lon).

Lag Features (Quan trọng)
Tạo các biến trễ từ dữ liệu quá khứ (ví dụ: prev_1d_*) để phục vụ bài toán dự báo.

2. Modeling Strategy

Chúng tôi tiếp cận theo hai hướng:

Diagnostic Model
Dùng các chỉ số hiện tại (UV Index, Cloud Cover, Wind Speed) để chẩn đoán lượng mưa.

Forecasting Model
Dùng dữ liệu quá khứ (Lag Features) để dự báo ngày tiếp theo.

Các thuật toán sử dụng

Linear Regression (Baseline)

Random Forest Regressor 🏆

Gradient Boosting / XGBoost / LightGBM

MLP Regressor (Neural Network cơ bản)

📊 Key Results
1. Hiệu năng Mô hình (Model Performance)
Target Variable	Best Model	R² Score	MAE	Insight
Nhiệt độ (Max Temp)	Gradient Boosting	~0.88	1.2°C	Dự báo rất chính xác nhờ chuỗi thời gian ổn định
Lượng mưa (Rainfall)	Random Forest	~0.42	4.2 mm	Khó dự báo do ngẫu nhiên cao nhưng bắt tốt xu hướng
2. Nghiên cứu Thực tiễn (Case Studies)
☀️ Question 1: Tiềm năng Năng lượng Tái tạo

Điện mặt trời
Đông Nam Bộ có bức xạ cao và ổn định quanh năm.
Miền Bắc bị hạn chế vào mùa Đông / Xuân.

Điện gió
Duyên hải Nam Trung Bộ & Tây Nguyên có tiềm năng gió lớn, phù hợp cho wind farms quy mô lớn.

✈️ Question 2: Tối ưu hóa Du lịch (Comfort Index)

Comfort Index dựa trên:

Nhiệt độ: 20–28°C

Độ ẩm: < 85%

Lượng mưa: < 5 mm

Kết luận
Tháng 11 và Tháng 12 là thời điểm vàng để du lịch xuyên Việt.

🚀 Advanced Feature: Real-time Storm Tracking

Dự án tích hợp Open-Meteo API để kiểm chứng mô hình với dữ liệu thực tế:

Khả năng

Lấy dữ liệu thời tiết hiện tại theo Lat / Lon

Kiểm chứng

Test trên các cơn bão năm 2025: Yagi, Trà Mi, Bão số 15

Kết quả

Random Forest có khả năng cảnh báo sớm mưa lớn với độ chính xác tốt về xu hướng.

🔮 Future Directions

Deep Learning: LSTM / GRU cho chuỗi thời gian dài hạn

Satellite Data: Theo dõi cloud cover theo thời gian thực

Radar: Dự báo mưa cực ngắn hạn (Nowcasting)
