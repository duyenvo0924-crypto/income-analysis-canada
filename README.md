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
  4. Tình trạng hôn nhân có ảnh hưởng đến thu nhập trung bình của cá nhân hay không?
  6. Thu nhập trung bình thay đổi như thế nào theo độ tuổi (Age_gap)? Có tồn tại một “điểm đỉnh” trong vòng đời thu nhập hay không?
  7. Tình trạng việc làm ảnh hưởng đến thu nhập như thế nào?
  8. Nguồn thu nhập chính của người dân đến từ đâu và mức độ đóng góp của từng nguồn là như thế nào?

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


# BÀI PHÂN TÍCH
# Cấu trúc dữ liệu
<img width="1228" height="673" alt="image" src="https://github.com/user-attachments/assets/0dfbfc4f-dee3-46f2-8c90-eab83659213e" />

# Phân tích 1: Thu nhập của các cá nhân trong dataset phân bố như thế nào?

### Giả thuyết: Thu nhập có xu hướng ở mức thu nhập thấp hoặc trung bình và chỉ một số ít có thu nhập rất cao.
| income_group   |   count |
|:---------------|--------:|
| 0-20k          |    2443 |
| 20k-40k        |    8408 |
| 40k-60k        |    9322 |
| 60k-80k        |    9672 |
| 80k-100k       |    9126 |
| 100k+          |   25713 |

### Biểu đồ:
<img width="702" height="368" alt="image" src="https://github.com/user-attachments/assets/d685f12e-93ef-4056-984d-02cdbc52b60b" />

### Kết luận: thu nhập không tập trung ở nhóm thấp như giả định ban đầu, mà ngược lại bị chi phối mạnh bởi nhóm thu nhập rất cao (100k+). Các nhóm thu nhập trung bình phân bố khá đồng đều, trong khi nhóm thu nhập thấp chiếm tỷ trọng nhỏ. Điều này cho thấy phân phối thu nhập trong dataset có xu hướng lệch về phía thu nhập cao.

# Phân tích 2: Trình độ học vấn có ảnh hưởng đến thu nhập không?

### Giả thuyết: Những cá nhân có trình độ học vấn cao hơn sẽ có thu nhập trung bình cao hơn.
| Highest_edu               |   Total_income |
|:--------------------------|---------------:|
| Bachelor Degree           |       123514   |
| Below High School         |        78467.2 |
| College / Diploma         |       105978   |
| High School               |       101793   |
| Postgraduate (Master/PhD) |       138171   |
| Unknown / Not Stated      |        85359.4 |

### Biểu đồ:
<img width="720" height="412" alt="image" src="https://github.com/user-attachments/assets/abf05b12-96fb-4ba0-9662-2478c7ab20f4" />

### Kết luận: Dữ liệu cho thấy trình độ học vấn có ảnh hưởng rõ rệt đến thu nhập: học vấn càng cao thì thu nhập trung bình càng lớn. Đồng thời, tồn tại chênh lệch thu nhập giữa nam và nữ trong tất cả các nhóm học vấn, với nam có xu hướng thu nhập cao hơn, tuy nhiên mức chênh lệch này tương đối ổn định và không quá lớn.

# Phân tích 3: Có sự khác biệt thu nhập giữa nam và nữ không?

### Giả thuyết: Nam giới có thu nhập trung bình cao hơn nữ giới.
| Gender   |   Total_income |
|:---------|---------------:|
| Female   |         108863 |
| Male     |         113634 |

### Biểu đồ:
<img width="689" height="366" alt="image" src="https://github.com/user-attachments/assets/6c2e25c1-8975-4964-9b6a-ff7927e1e77f" />

### Kết luận: Dữ liệu cho thấy tồn tại chênh lệch thu nhập theo giới tính, với nam có thu nhập trung bình cao hơn nữ. Tuy nhiên, mức chênh lệch tương đối nhỏ (~4%), cho thấy khoảng cách thu nhập là có nhưng không quá lớn trong dataset này.

# Phân tích 4: Tình trạng hôn nhân có ảnh hưởng đến thu nhập trung bình của cá nhân hay không?
### Giả thuyết: Những người đã kết hôn có xu hướng thu nhập cao hơn so với những người chưa kết hôn hoặc đã ly hôn.
| Marital_status   |   Total_income |
|:-----------------|---------------:|
| Divorced         |          77109 |
| Married          |         118724 |
| Single           |         122935 |
| Widowed          |         104831 |

### Biểu đồ:
<img width="702" height="391" alt="image" src="https://github.com/user-attachments/assets/03f0a2d8-0415-4997-b736-c48722fe2dce" />

### Kết luận: Dữ liệu cho thấy tình trạng hôn nhân có ảnh hưởng đến thu nhập, tuy nhiên không theo hướng giả định ban đầu. Người độc thân có thu nhập trung bình cao nhất, trong khi người đã kết hôn đứng thứ hai. Nhóm ly hôn có thu nhập thấp nhất, cho thấy tình trạng hôn nhân có thể liên quan đến sự ổn định tài chính, nhưng không phải là yếu tố quyết định duy nhất.

# Phân tích 5: Thu nhập trung bình thay đổi như thế nào theo độ tuổi (Age_gap)? Có tồn tại một “điểm đỉnh” trong vòng đời thu nhập hay không?
### Giả thuyết: Thu nhập tăng dần theo độ tuổi trong giai đoạn đầu sự nghiệp, đạt mức cao nhất ở nhóm trung niên, sau đó giảm dần ở các nhóm tuổi lớn hơn.
  Age_gap |   Total_income |
|----------:|---------------:|
|         1 |       116134   |
|         2 |       121822   |
|         3 |       131480   |
|         4 |       143716   |
|         5 |       128134   |
|         6 |       103008   |
|         7 |       110007   |
|         8 |       117014   |
|         9 |       126677   |
|        10 |       136084   |
|        11 |       132961   |
|        12 |       117105   |
|        13 |       102257   |
|        14 |        86528.7 |
|        15 |        70890   |

### Biểu đồ:
<<img width="704" height="391" alt="image" src="https://github.com/user-attachments/assets/9f33604c-f5c8-4375-96ca-f052743d12a7" />

### Kết luận: Dữ liệu cho thấy thu nhập trung bình không tăng tuyến tính theo độ tuổi mà có dạng “hình chuông” (inverted U-shape). Thu nhập tăng dần ở các nhóm tuổi trẻ, đạt đỉnh ở nhóm trung niên, sau đó giảm dần ở các nhóm tuổi cao hơn. Điều này phản ánh quy luật vòng đời thu nhập, trong đó thu nhập cao nhất đạt được khi cá nhân tích lũy đủ kinh nghiệm và đạt vị trí nghề nghiệp ổn định.

# Phân tích 6: Số giờ làm việc có ảnh hưởng đến thu nhập không?

### Giả thuyết: Những người làm việc nhiều giờ hơn có thu nhập cao hơn.
| hour_group   |   Total_income |
|:-------------|---------------:|
| 0-20         |        92338.2 |
| 20-40        |        99924.6 |
| 40-60        |        97230.3 |
| 60-80        |       106251   |

### Biểu đồ:
<img width="638" height="390" alt="image" src="https://github.com/user-attachments/assets/42adc7be-d3de-4687-b689-0d766f8828be" />

### Kết luận: Dữ liệu cho thấy thu nhập có xu hướng tăng theo số giờ làm việc, đặc biệt ở nhóm làm việc rất nhiều giờ (60–80 giờ/tuần). Tuy nhiên, mối quan hệ này không hoàn toàn tuyến tính do tồn tại nhóm 40–60 giờ có thu nhập thấp hơn các nhóm khác. Điều này cho thấy ngoài số giờ làm việc, các yếu tố như loại công việc, hình thức trả lương và ngành nghề cũng ảnh hưởng đáng kể đến thu nhập.

# Phân tích 7: Tình trạng việc làm ảnh hưởng đến thu nhập như thế nào?

### Giả thuyết: Những cá nhân đang làm việc có thu nhập cao hơn những người không làm việc.
| Work_ref            |   Total_income |
|:--------------------|---------------:|
| Employed            |       125870   |
| Not in labour force |       123514   |
| Unemployed          |        75723.2 |

### Biểu đồ:
<img width="638" height="366" alt="image" src="https://github.com/user-attachments/assets/eca44452-ce5e-4f20-9e73-4f0323009be5" />

### Kết luận: Dữ liệu cho thấy những người có việc làm có thu nhập trung bình cao nhất, trong khi nhóm thất nghiệp có thu nhập thấp hơn đáng kể. Tuy nhiên, nhóm không tham gia lực lượng lao động lại có mức thu nhập gần tương đương với nhóm có việc làm, cho thấy thu nhập không chỉ phụ thuộc vào tình trạng việc làm mà còn có thể đến từ các nguồn khác như đầu tư hoặc tài sản.

# Phân tích 8: Nguồn thu nhập chính của người dân đến từ đâu và mức độ đóng góp của từng nguồn là như thế nào?
### Giả thuyết: Thu nhập từ lương (salary) chiếm tỷ trọng lớn nhất trong tổng thu nhập, trong khi các nguồn như đầu tư, tự kinh doanh và lương hưu chiếm tỷ trọng nhỏ hơn.
| Income_source   | Total_amount   |
|:----------------|:---------------|
| Salary_wages    | 5,649,484,875  |
| Self_emp_income | 101,404,375    |
| Investment      | 169,875,700    |
| Pension         | 556,811,000    |

### Biểu đồ:
<img width="641" height="369" alt="image" src="https://github.com/user-attachments/assets/be373779-eb6d-43f5-bec0-ba40d1dbd837" />

### Kết luận: Dữ liệu cho thấy thu nhập chủ yếu đến từ tiền lương (Salary_wages), chiếm tỷ trọng áp đảo trong tổng thu nhập. Các nguồn thu khác như lương hưu (Pension), đầu tư (Investment) và tự kinh doanh (Self_employment) đóng góp tỷ lệ nhỏ hơn đáng kể. Điều này cho thấy thu nhập của cá nhân trong dataset phụ thuộc mạnh vào nguồn thu từ lao động chính.

# Tổng kết: 
Thu nhập tại Canada không chỉ phụ thuộc vào việc một người làm nhiều hay ít, mà chủ yếu được quyết định bởi vị thế của họ trong nền kinh tế, bao gồm trình độ kỹ năng, loại công việc và giai đoạn phát triển trong sự nghiệp. Bên cạnh đó, các yếu tố như giới tính, tình trạng hôn nhân và việc có tham gia lao động hay không cũng tạo ra sự khác biệt về thu nhập giữa các nhóm, nhưng chỉ đóng vai trò bổ trợ và phản ánh bối cảnh kinh tế – xã hội của từng cá nhân, chứ không phải là yếu tố quyết định chính.
