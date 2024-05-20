# Các tiêu chí đánh giá

# Mở đầu 
 - Các tiêu chí đánh giá cho các mô hình phân loại cung cấp đánh giá định lượng (quantitive assessment) về hiệu suất 
 - Lựa chọn metric dựa vào cụ thể của vấn đề -> chọn các đánh giá fit với vấn đề
 - Qtrong là dựa vào sai số -> chọn tiêu chí đánh giá
    + False positive - Sai số loại 1 
        * Dự đoán nhầm 
    + False negative - Sai số loại 2 
        * Không nhận ra đối tượng thuộc về 1 lớp nào đó -> bỏ sót 

## Confusion matrix
- Fundametal tool trong đánh giá mô hình phân loại 
### Các thành phần 
- Bao gồm 4 thành phần
    1. True Positive (TP): Số các positive instance được phân loại đúng bới mô hình 
    2. False Positive (FP): Số các thành phần âm nhưng được phân loại là dương (VD: không có bệnh -> có bệnh)
    3. True Negative (TN): Âm tính được phân loại đúng là âm tính. (VD: không có bệnh được dự đoán là không có bệnh)
    4. False Negative (FN): Số các thành phần dương nhưng dự đoán là âm 
#### Accuracy 
- Tỉ số giữa những phân loại đúng / toàn bộ phân loại.
- Acc cao -> tỉ lệ dự đoán đúng cao >< Acc thấp -> dự đoán sai nhiều 
- Accuracy = $$\frac{(TP + TN)} {(TP + TN + FP + FN)}$$
#### Precision 
- Đo lường tỷ lệ True positve (TP) trong tổng thể được phân loại vào TP
- Đo sự chính xác của dự đoán positive predictions
- Pre cao có ý nghĩa rằng mô hình có thể phân loại tốt các positive >< Pre thấp -> dự đoán FP nhiều 
- Precision = $$\frac{TP}{(TP+FP)}$$
#### Recall 
- Tỷ lệ các dự đoán đúng / tập thật sự đúng 
- sử dụng kết hợp với các metrics đánh giá khác F1-Score và acc 
- AKA sentivity hoặc True positive (TPR): đo tỷ lệ dự đoán positive trong tập dữ liệu
-> khả năng nhận diện được đúng các trường hợp positive. đánh giá tỷ lệ các trường hợp mà mô hình đã phân loại đúng,
- ví dụ: 
    - có 100 người mắc bệnh. Mô hình phân loại được 80 người mắc bệnh :TP
    - Thì lúc này Recall = $\frac{Tp}{TP+LN}$ = $\frac{80}{80+20}$ = 0.8
    --->> Điều này có nghĩa Recall của mô hình là 80%, tức là mô hình có khả năng phát hiện đúng 80% các trường hợp dương tính 
##### Tầm quan trọng của RECALL
- quan trọng trong các trường hợp positive bị bỏ sót 
##### Cải thiện hệ số RECALL
1. Tối ưu hoá ngưỡng phân loại 
2. Thu thập và gán nhãn thêm dữ liệu 
3. Xử lý dữ liệu không cân bằng 
4. Cải thiện đặc trưng (Feature Engineer)
5. Sử dụng được mô hình mới 
6. Điều chỉnh các tham số 
7. Tập trung các thuật toán vào recall

#### F1-score
- Kết hợp của Precision và recall để đánh giá mô hình 
- Đo lường trung bình điều hoà (harmonic mean) - đặt tầm quan trọng như nhau cho cả 2 chỉ số 
- Công thức F1 = $2*\frac{Pre*Recall}{Pre+Recall}$
##### Thành phần 
- Pre
- Recall - độ nhạy 
##### Quan trọng 
- Nếu 1 trong 2 tham số thấp F1 cũng sẽ thấp 
##### Các trường hợp không nên sử dụng Recall
- Dữ liệu không cân bằng giữa các lớp (Lớp A ít hơn lớp B) >> Acc
- Trọng số bằng nhau: không ưu tiên Recall hoặc Pre
##### Trung bình điều hoà 
- Không bị ảnh hưởng bởi outlier

#### F-Beta score
- Biến thể của F1
- Cho phép điều chỉnh mức độ quan trọng của Pre và Recal 
