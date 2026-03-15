# Phân tích phân bố thu nhập và các yếu tố ảnh hưởng đến thu nhập tại Canada
# 1. Giới thiệu
   
Thu nhập của người dân là một trong những chỉ số quan trọng phản ánh mức sống và sự phát triển kinh tế của một quốc gia. Việc phân tích phân bố thu nhập giúp chúng ta hiểu rõ hơn về sự chênh lệch thu nhập trong xã hội cũng như các yếu tố ảnh hưởng đến thu nhập của cá nhân.

Mục tiêu của bài phân tích này là:

1. Phân tích dữ liệu khảo sát thu nhập nhằm hiểu rõ hơn về phân bố thu nhập, xu hướng việc làm và mức độ ổn định kinh tế của người dân tại Canada.

2. Thông qua việc phân tích dữ liệu, dự án sẽ xem xét mối quan hệ giữa thu nhập và các yếu tố như đặc điểm nhân khẩu học, trình độ học vấn, tình trạng việc làm và số giờ làm việc.

3. Việc phân tích này giúp làm rõ các yếu tố có thể ảnh hưởng đến thu nhập của cá nhân và cung cấp cái nhìn tổng quan về tình hình kinh tế và thị trường lao động trong dataset.

Khám phá mối quan hệ giữa thu nhập với các yếu tố như:

  1. độ tuổi

  2. giới tính
  
  3. trình độ học vấn
  
  4. tình trạng nhập cư
  
  5. nguồn thu nhập
  
Thông qua việc sử dụng các kỹ thuật Exploratory Data Analysis (EDA) và trực quan hóa dữ liệu, bài phân tích nhằm đưa ra những nhận định có ý nghĩa về cấu trúc thu nhập trong xã hội.

Các câu hỏi nghiên cứu chính của bài phân tích gồm:
  1. Thu nhập của người dân Canada phân bố như thế nào?
  2. Trình độ học vấn có ảnh hưởng đến thu nhập hay không?
  3. Thu nhập có khác biệt giữa nam và nữ không?
  4. Thu nhập thay đổi như thế nào theo độ tuổi?
  5. Người nhập cư có mức thu nhập khác so với người bản địa không?
  6. Nguồn thu nhập chính của người dân là gì?


# 2. Mô tả dữ liệu

Dataset được sử dụng trong bài phân tích là Income Survey Dataset, bao gồm thông tin khảo sát về thu nhập và các đặc điểm nhân khẩu học của người dân Canada.

Dataset bao gồm:

72,643 quan sát

38 biến dữ liệu

Mỗi dòng dữ liệu đại diện cho một cá nhân trong khảo sát.

Dataset chứa các thông tin liên quan đến:

1. đặc điểm nhân khẩu học

2. tình trạng việc làm

3. nguồn thu nhập

4. các khoản trợ cấp xã hội

# Các biến quan trọng sử dụng trong phân tích
PersonID: Mã định danh duy nhất của mỗi cá nhân trong dataset.

- Gender: Giới tính của cá nhân (Nam/Nữ).

- Age_gap: Nhóm tuổi của cá nhân.

- Marital_status: Tình trạng hôn nhân của cá nhân (độc thân, đã kết hôn, ly hôn,…).

- Province: Tỉnh hoặc khu vực nơi cá nhân sinh sống.

- Highest_edu: Trình độ học vấn cao nhất mà cá nhân đạt được.

- Work_ref: Tình trạng việc làm của cá nhân trong thời điểm khảo sát.

- Work_yearly: Thông tin về việc cá nhân có tham gia lao động trong năm hay không.

- Total_hour_ref: Tổng số giờ làm việc của cá nhân trong khoảng thời gian tham chiếu.

- Salary_wages: Thu nhập của cá nhân từ lương hoặc tiền công lao động.

- Self_emp_income: Thu nhập từ hoạt động tự kinh doanh.

- Investment: Thu nhập từ các khoản đầu tư tài chính.

- Pension: Thu nhập từ lương hưu.

- Cap_gain: Thu nhập từ lãi vốn (capital gains).

- CPP_QPP: Thu nhập từ chương trình lương hưu công cộng.

- Emp_insurance: Thu nhập từ bảo hiểm thất nghiệp.

- Child_benefit: Trợ cấp dành cho gia đình có con nhỏ.

- Guaranteed_income: Trợ cấp thu nhập từ chính phủ.

- Total_income: Tổng thu nhập của cá nhân từ tất cả các nguồn.

# 3. Phương pháp phân tích (Methodology)

Quy trình phân tích dữ liệu trong bài này bao gồm các bước chính sau:

1. Data Understanding:
Tìm hiểu cấu trúc dữ liệu và ý nghĩa của các biến.

2. Data Cleaning:
Làm sạch dữ liệu, xử lý missing values và chuẩn hóa dữ liệu.

3. Exploratory Data Analysis (EDA):
Phân tích khám phá dữ liệu để tìm ra các xu hướng và mối quan hệ.

4. Data Visualization:
Sử dụng Power BI để trực quan hóa kết quả phân tích.

5. Insight & Conclusion:
Rút ra các nhận định quan trọng từ dữ liệu.

# Các công cụ sử dụng trong quá trình phân tích:

1. Python (Google Colab): Data Cleaning và EDA

2. Power BI: Trực quan hóa dữ liệu

3. Github: Trình bày báo cáo
