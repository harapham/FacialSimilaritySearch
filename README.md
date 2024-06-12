
**Hệ thống tìm kiếm khuôn mặt tương tự.**
- hệ thống thực hiện so sánh sai số về 2 đặc trưng trên khuôn mặt là màu da và các điểm chính trên khuôn mặt.
- trong đó có sử dụng Kmeans, lọc phân ngưỡng màu da, làm mịn ảnh, detected face, find landmark,.... 
- khi so sánh màu sắc sử dụng CIE2000, so sánh vị trí điểm trên khuôn mặt bằng khoảng cách Euclide dựa trên các giá trị tỉ lệ diện tích và các góc
**	Thuộc tính đặc trưng về màu da
Thực hiện trích rút đặc trưng là bộ màu RGB mô tả tông màu da chủ đạo của khuôn mặt. 
Định dạng đặc trưng:
feature_skin=[R,G,B]
với R,G,B là tham số màu sắc của 3 màu red,green,blue có khoảng tử 0-255
**	Thuộc tính đặc trưng về các điểm trên khuôn mặt
Thực hiện trích rút đặc trưng là bộ tỉ lệ diện tích của 6 tam giác và 18 góc được hình thành từ các vector tạo nên từ 7 điểm chính trên khuôn mặt
Định dạng đặc trưng 24 phần tử: 
feature_point=[A_1,A_2,…,A_6,a_1,a_2,…,a_18 ]  
với A_1,A_2,…,A_6  là bộ tỉ lệ diện tích của 6 tam giác,a_1,a_2,…,a_18  là bộ 18 góc
![image](https://github.com/harapham/FacialSimilaritySearch/assets/93029503/99c441d9-6c8a-4682-94fd-29fd66d8b7d5)

**	Bộ thuộc tính đặc trưng tổng hợp:
feature={[R^i,G^i,B^i,A_1^i,A_2^i,…,A_6^i,a_1^i,a_2^i,…,a_18^i ],i∈(1,n)}

