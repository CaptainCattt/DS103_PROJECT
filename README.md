# DS103_PROJECT
# Xây dựng bộ dữ liệu dự đoán giá Laptop cũ thu  thập từ trang thương mại điện tử FPT Shop

# 1.	Giới thiệu
 Trong đề tài này, chúng tôi xây dựng bộ dữ liệu về thông số và giá cả của laptop cũ từ trang thương mại điện tử “FPTShop.com.vn” và thực hiện việc đào tạo mô hình máy học đơn giản để đánh giá. Sau khi hoàn thành, chúng tôi có thể phát triển bộ dữ liệu về độ cụ thể và đa dạng, xây dựng và đào tạo mô hình máy học phù hợp với bộ dữ liệu này hơn.

  - Input: Thông số của một chiếc laptop cũ.
  - Output: Nhãn giá được dữ đoán cho cho chiếc laptop đó.
Ví dụ: 
 - Input: thông tin về 1 chiếc laptop cũ.
 - Output: giá dự đoán của laptop đó.

# 2. Dữ liệu
# 2.1 Thu thập dữ liệu

 Chúng tôi đã thu thập dữ liệu về thông số và giá cả của laptop cũ trên trang thương mại điện tử FPT Shop. Sử dụng tiện ích Google Chrome: Google tìm kiếm, Google Colab, Python Visual Code để chạy code thu thập. Chúng tôi thu được khoảng từ 10 – 20 dữ liệu cụ thể về laptop cũ trong 1 lần tải.

# 2.2 Thông tin về bộ dữ liệu

![image](https://github.com/CaptainCattt/DS103_PROJECT/assets/133556107/4f26be6c-75d1-4354-b3a9-a7c54f7f17f3)

 TinyData là một tập dữ liệu được chúng tôi thu thập trên mạng internet. Cụ thể là thu thập tại nguồn: https://fptshop.com.vn/. Tập dữ liệu này chứa 1572 dòng dữ liệu về thông số và giá cả của laptop cũ, với file RawData khi thu thập có đến hơn 70 thuộc tính. Sau khi cân nhắc và để tối ưu hóa khi đưa vào mô hình học máy, File TidyData chỉ giữ lại 703 dòng dữ liệu và 28 thuộc tính. 
 
 Link bộ dữ liệu: https://drive.google.com/drive/u/4/folders/1hUA49DjfRywdjm4BxGTuzBplYv2Jciw3 ?fbclid=IwAR0KAQPtMdwlqzh30JbqABsgDIDlplTz4D2_O6LM0cscTEYPE4z8YU RsAvA

# 2.3 Khảo sát dữ liệu

![image](https://github.com/CaptainCattt/DS103_PROJECT/assets/133556107/7c506ecf-03db-4703-ae55-ba3bf4af6742)

# 2.4 Phương pháp xử lý dữ liệu

Đầu tiên, chúng tôi thực hiện lấy dữ liệu tự động của các laptop cũ ở trên FPT Shop 
thành một file excel. Tiếp đến dử dụng Google Colab để thực hiện thao tác với bộ dữ 
liệu đã thu thập được.

 - Tiến hành upload file excel đã có lên drive.
 - Từ Colab sử dụng thư viện thư viện pandas, numpy và re để chuyển file excel đã upload thành file csv để dễ thao tác.
 - Dùng pd.read_csv để tiến hành đọc dữ liệu của file.
 - Tiếp theo xóa các cột thuộc tính không cần thiết với bài làm cũng như các cột thuộc tính không quan trọng, những cột thuộc tính mà người dùng ít khi quan tâm khi mua máy (“Thiết kế & Trọng lượng.Kích thước", "Bộ xử lý.Hãng CPU",…).
 - Đưa các cột có đơn vị đo lường về dạng số hoặc thuần ký tự (“Nhôm”, “nhựa”,…) để dễ dàng thuận tiện cho việc xử lí dữ liệu sau này.
 - Chỉnh sửa các ô dữ liệu NULL trong quá trình lấy dữ liệu về bị thiếu sót.
 - Đổi tên các cột bị sai bị thiếu thành các cột mới hoàn chỉnh.
 - Tiến hành lọc lại các thuộc tính không cần thiết sau khi đã chỉnh sửa.
 - 
Qua đó chúng tôi thu được bộ dữ liệu mới (TinyData) từ bộ dữ liệu cũ (RawData) từ 1572 rows x 78 columns thành 703 rows x 28 columns.

# 2.5 Đánh giá tập dữ liệu đã xử lý

 - Dữ liệu có nhiều thuộc tính có kiểu khác nhau, cần được tiền xử lý trước khi thực hiện huấn luyện.
 - Tập dữ liệu có kích thước nhỏ khi so với các công trình khác, nhưng đủ để thực hiện nghiên cứu trong đồ án này.
 - Tập train và tập test được chia theo đúng tỉ lệ 8:2.

# 3. Phương pháp máy học

# 3.1 Mô hình máy học
 - Mô hình Linear regression:
 - Mô hình Decision tree:
 
# 3.2 Công cụ sử dụng
 Nền tảng sử dụng: Google Colab.
 
# 3.3 Các phương pháp đánh giá
 Confusion matrix: Giúp đánh giá được các giá trị cụ thể mỗi loại được phân loại như thế 
nào, lớp nào được phân loại đúng nhiều nhất, và dữ liệu thuộc lớp nào hay bị phân loại 
nhầm vào lớp khác.
 - True Positive (TP): Giá trị dự đoán khớp với giá trị thực tế. Nhãn dương tính 
được dự đoán là dương tính.
 - True Negative (TN): Giá trị dự đoán khớp với giá trị thực tế. Nhãn âm tính được 
dự đoán là âm tính.
 - False Positive (FP): Giá trị dự đoán bị sai. Nhãn âm tính bị dự đoán là dương 
tính.
 - False Negative (FN): Giá trị dự đoán bị sai. Nhãn dương tính bị dự đoán là âm 
tính.

Chúng tôi sử dụng 2 độ đo sau đây để đánh giá mô hình:
 - F1-score
 - Accuracy

# 4 Kết luận
# 4.1 Kết quả đạt được
- Đồ án đạt mục tiêu đã được đề ra từ đầu, đó là xây dựng được một mô hình cho kết quả 
đạt độ chính xác khoảng 70% (SVC đạt 70%) 
- Tìm hiểu, sử dụng được một số phương pháp tiền xử lý ảnh có thể ứng dụng trong các 
bài toán tương tự.
- Tìm hiểu và tiếp cận được nhiều phương pháp máy học cho bài toán phân lớp đa lớp. Có 
cái nhìn cơ bản tổng thể về Machine Learning.
# 4.2 Khó khăn gặp phải
- Thiếu kinh nghiệm giải quyết các bài toán xử lý dữ liệu có nhiều thuộc tính nói riêng và 
các bài toán Machine Learning nói chung dẫn đến việc gặp nhiều khó khăn trong quá 
trình thu thập cũng như xử lý dữ liệu.
- Đã sử dụng nhiều phương pháp xử lý dữ liệu nhưng một số lỗi vẫn không cho kết quả 
khả quan. 
- Hạn chế về kiến thức nền khiến cho việc tiếp cận các phương pháp xử lý dữ liệu cũng 
như tinh chỉnh mô hình trong python tương đối khó khăn.





