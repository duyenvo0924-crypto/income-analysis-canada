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

|    |   PersonID |   Weight |   Province |   MBMREGP |   Age_gap |   Gender |   Marital_status |   Highschool |   Highest_edu |   Work_ref |   Work_yearly |   Emp_week_ref |   Total_hour_ref |   paid_emp_ref |   self_emp_ref |   Immigrant |   Year_immigrant |  income_after_tax    |   Cap_gain |   Childcare_expe |   Child_benefit |   CPP_QPP |   Earning |   Guaranteed_income |   Investment |   Old_age_pension |   Private_pension |   Self_emp_income |   Pension |   Self_emp_income.1 |  Total_income    |   Emp_insurance |  Salary_wages    |   compensation |   Family_mem |   CFCOMP |   CONDMP |    RENTM |
|---:|-----------:|---------:|-----------:|----------:|----------:|---------:|-----------------:|-------------:|--------------:|-----------:|--------------:|---------------:|-----------------:|---------------:|---------------:|------------:|-----------------:|:---------------------|-----------:|-----------------:|----------------:|----------:|----------:|--------------------:|-------------:|------------------:|------------------:|------------------:|----------:|--------------------:|:-----------------|----------------:|:-----------------|---------------:|-------------:|---------:|---------:|---------:|
|  0 |          1 |  139.65  |         59 |        38 |        15 |        2 |                3 |            1 |             3 |          2 |            30 |             96 |             9996 |              6 |              6 |           2 |                6 | 20,275               |          0 |                0 |               0 |      5000 |         0 |                7750 |            0 |              7000 |                 0 |                 0 |         0 |                   0 | 20,275           |               0 | -                |              0 |            1 |        1 | 99999996 | 99999996 |
|  1 |          2 |  254.104 |         35 |        17 |         9 |        1 |                1 |            1 |             2 |          1 |            11 |             52 |             2080 |              1 |              2 |           2 |                6 | 61,680               |          0 |                0 |               0 |         0 |     70000 |                   0 |            0 |                 0 |                 0 |                 0 |         0 |                   0 | 110,875          |               0 | 106,000          |              0 |            4 |        4 | 99999996 | 99999996 |
|  2 |          3 |  254.104 |         35 |        17 |         9 |        2 |                1 |            1 |             3 |          1 |            11 |             52 |             2080 |              1 |              2 |           2 |                6 | 26,875               |          0 |                0 |            4500 |         0 |     22000 |                   0 |            0 |                 0 |                 0 |                 0 |         0 |                   0 | 110,875          |               0 | 106,000          |              0 |            4 |        4 | 99999996 | 99999996 |
|  3 |          4 |  254.104 |         35 |        17 |         4 |        1 |                4 |            2 |             1 |          1 |            11 |             52 |             2080 |              1 |              2 |           2 |                6 | 14,000               |          0 |                0 |               0 |         0 |     14000 |                   0 |            0 |                 0 |                 0 |                 0 |         0 |                   0 | 110,875          |               0 | 106,000          |              0 |            4 |        4 | 99999996 | 99999996 |
|  4 |          5 |  254.104 |         35 |        17 |         3 |        1 |               96 |            6 |             6 |          6 |            96 |             96 |             9996 |              6 |              6 |           6 |                6 | 99,999,996           |   99999996 |         99999996 |        99999996 |  99999996 |  99999996 |            99999996 |     99999996 |          99999996 |          99999996 |          99999996 |         0 |                   0 | 110,875          |               0 | 106,000          |              0 |            4 |        4 | 99999996 | 99999996 |
|  5 |          6 |  738.808 |         24 |        12 |        12 |        2 |                3 |            1 |             2 |          1 |            11 |             52 |             1950 |              1 |              2 |           2 |                6 | 42,200               |          0 |                0 |            5500 |         0 |     27000 |                   0 |            0 |                 0 |                 0 |                 0 |         0 |                   0 | 75,775           |               0 | 59,500           |            100 |            3 |        6 | 99999996 |      600 |
|  6 |          7 |  738.808 |         24 |        12 |         4 |        1 |                4 |            2 |             1 |          1 |            22 |             12 |              180 |              1 |              2 |           2 |                6 | 7,500                |          0 |                0 |               0 |         0 |      7500 |                   0 |            0 |                 0 |                 0 |                 0 |         0 |                   0 | 75,775           |               0 | 59,500           |            100 |            3 |        6 | 99999996 |      600 |
|  7 |          8 |  738.808 |         24 |        12 |         5 |        1 |                4 |            9 |             9 |          1 |            22 |             40 |             1000 |              1 |              2 |           2 |                6 | 23,965               |          0 |                0 |               0 |         0 |     25000 |                   0 |            0 |                 0 |                 0 |                 0 |         0 |                   0 | 75,775           |               0 | 59,500           |            100 |            3 |        6 | 99999996 |      600 |
|  8 |          9 |  538.412 |         24 |        14 |        15 |        2 |                3 |            1 |             2 |          2 |            30 |             96 |             9996 |              6 |              6 |           2 |                6 | 21,050               |          0 |                0 |               0 |      6500 |         0 |                6250 |            0 |              7000 |                 0 |                 0 |         0 |                   0 | 21,050           |               0 | -                |              0 |            1 |        1 | 99999996 |      400 |
|  9 |         10 | 1227.69  |         24 |        10 |         9 |        1 |                1 |            1 |             4 |          1 |            21 |             32 |             1280 |              1 |              2 |           1 |                3 | 31,270               |          0 |                0 |               0 |         0 |     28000 |                   0 |            0 |                 0 |                 0 |                 0 |         0 |                   0 | 77,000           |           21500 | 43,500           |              0 |            4 |        4 | 99999996 | 99999996 |



 

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
