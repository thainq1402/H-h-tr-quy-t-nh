# Guide line 

## Các hướng tiếp cận 
## 0. Khai phá dữ liệu 
- Khai phá dữ liệu quan tâm các đặc tính sau của bộ dữ liệu:
    + Các trường dữ liệu đã đúng định dạng -> all
    + Check missing data -> all 
    + Các chỉ số thống kê : mean, median, min, max.... 
        -> 1 số biểu đồ: Line chart, Box plot -> out line, 
- Khai phá dữ liệu chuỗi thời gian:
    + Biểu đồ line chart 
    + Rolling mean 
        -> Moving AVG: smooth price data -> cut down noise -> show được rõ tính trend -> Chọn model phù hợp với trend
        -> ví dụ: nếu MA cho ta thấy rằng đang có trend upward và Rolling std rất nhỏ cho thấy rằng có thể có trend tăng -> mô hình hồi quy tuyến tính (Nếu trend tuyến tính ) hoặc Random forest hoặc Gradient Boosting nếu quna hệ giữa các feature là không tuyến tính.
    + Rolling Std: the standard of closing prices of VN-Index past 30 days -> show the deviation 
        -> detect the period that the deviation go out line -> ARCH 
        -> Phát hiện outline -> cân nhắc bỏ hoặc là để lại để chọn mô hình phù hợp với outline: Random forest hoặc SVM với kernel function : hiệu quả trong việc handle outlies không bị ảnh hưởng bởi nó
    + Ma trận hệ số tương quan
        -> giữa các chuỗi với nhau 
            + VN index với Dow jones
    + Phân rã chuỗi thời gian: Trend, Seasonality, Noise...
    + ACF, PACF

### Dự báo ngắn hạn với dữ liệu từ tuần cuối tháng 4 
- AR:  
- MA: có tính mùa 
- ARIMA: 
- Holt-winter: có tính mùa 
- LSTM: 
### Dài hạn dự báo với dữ liệu từ đầu năm
- ARIMA:
- Holt-winter:
- LSTM:
- ARCH:
- GARCH:
- SARIMA:
- XGBOOST:
- Prophet:
- Link các mô hình khác: https://github.com/ml-tooling/best-of-ml-python?tab=readme-ov-file#time-series-data


