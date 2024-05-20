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
- Accuracy = (TP + TN) / (TP + TN + FP + FN)
- Accuracy = $$\frac{(TP + TN)} {(TP + TN + FP + FN)}$$