---
icon: question
---

# Interview question

##

## 1. Overview



<details>

<summary>Bạn hãy giải thích sự khác biệt giữa <strong>AI, Machine Learning, và Deep Learning</strong></summary>

* Ai là trí thông minh được thể hiện bằng máy móc, dùng để mô tả các máy móc có khả năng bắt chước các chức năng của con người&#x20;
* Machine learning là một nhánh của AI, xoay quanh việc nghiên cứu và xây dựng các kĩ thuật cho phép hệ thống "học" tự động từ dữ liệu để giải quyết những vấn đề cụ thể.
* Deep Learning là một nhánh của Machine Learning sử dụng các mạng nơ-ron nhân tạo nhiều tầng để học cách biểu diễn dữ liệu phức tạp.

&#x20;![](<../.gitbook/assets/image (43).png>)<img src="../.gitbook/assets/image (45).png" alt="" data-size="original">



</details>

<details>

<summary>Những yếu tố nào bạn cần xem xét khi chọn một mô hình AI cho bài toán cụ thể?</summary>

* Yêu cầu bài toàn: loại bài toán và mục tiêu đặt ra&#x20;
* Dữ liệu:&#x20;
  * Chất lượng và số lượng dữ liệu lớn phức tạp - DL, nhỏ cần ưu tiên như DT, LR
  * Cấu tạo dữ liệu: Cấu trúc hay phi cấu trúc
  * Tiền xử lý dữ liệu
* Đô phức tạp và khả năng diễn giải của bài toán
* Hiệu năng và tốc độ
* Tài nguyên và kỹ thuật
* Môi trường triển khai
* Yêu cầu đặc thù

</details>

## 2. Machine Learning

<details>

<summary>Hãy mô tả quy trình xây dựng một mô hình Machine Learning từ đầu.</summary>

1. Xác định vấn đề.
2. Thu thập và phân tích dữ liệu.
3. Tiền xử lý và chia tập dữ liệu.
4. Lựa chọn và huấn luyện mô hình.
5. Đánh giá và tối ưu hóa mô hình.
6. Triển khai và bảo trì.

</details>

<details>

<summary>Supervised Learning và Unsupervised Learning khác nhau như thế nào</summary>

Supervised Learning sử dụng sử dữ liệu có gán nhãn để huấn luyện còn Unsupervised Learning thì không

ví dụ:

* Supervised Learning:&#x20;
  * Phân loại spam email
  * Phân loại ảnh các loại động vật
* Unsupervied Learning:
  * Phân nhóm người dùng dựa trên hành vi mua sắm
  * Recomanender system

</details>

<details>

<summary>Bạn có thể giải thích ý nghĩa của các thuật ngữ như <strong>bias</strong>, <strong>variance</strong>, và <strong>trade-off</strong> của chúng không?</summary>

* **Bias**: Đo lường sự sai lệch của mô hình so với thực tế. Bias cao dẫn đến underfitting.
* **Variance**: Đo lường độ nhạy cảm của mô hình với dữ liệu huấn luyện. Variance cao dẫn đến overfitting.
* **Bias-Variance Trade-off**: Quá trình tìm mức cân bằng giữa bias và variance để đạt hiệu suất tối ưu.

![](../.gitbook/assets/ML--Bias-Vs-Variance.png)

</details>

<details>

<summary>Bạn sẽ xử lý Missing data như thế nào?</summary>

* Xác định vị trí , số lượng (%)
* Phân tích&#x20;
* Xử lý:
  * Loại bỏ (nếu <5%)
  * Thay thế :
    * Điền giá trị mean, median, mode
    * Giá trị lân cận trước hoặc sau
    * Giá trị dự đoán
    * Giá trị theo nhóm

</details>

<details>

<summary>Điểm khác biệt giữa L1(Lasso) và L2 (Ridge) Regularization là gì ?</summary>

Cả **L1** và **L2 regularization** đều là kỹ thuật được sử dụng để tránh **overfitting** trong các mô hình Machine Learning, đặc biệt là hồi quy.

* **L1 (Lasso)**: Loại bỏ đặc trưng không quan trọng, phù hợp với dữ liệu thưa thớt.\
  $$Loss= MSE + \lambda \displaystyle{\sum_{i=1}^n|w_i|}$$
* **L2 (Ridge)**: Giảm overfitting và giữ lại tất cả đặc trưng.\
  $$Loss= MSE + \lambda \displaystyle{\sum_{i=1}^n w_i^2}$$

</details>

<details>

<summary>Phân biệt Precision và Recall (hoặc lỗi loại 1 và lỗi loại 2)?</summary>

* Precesion Tỷ lệ số lượng mẫu dự đoán đúng $$\frac{TP}{TP+FP}$$ trên tổng số dự đoán đúng&#x20;
* Recall: Tỷ lệ số lượng mẫu dự đoán đúng trên  $$\frac{TP}{TP+FN}$$ trên tổng số dự đoán có kết quả chính xác là đúng

</details>

<details>

<summary>Điểm khác biệt giữa Bagging và Boosting là gì</summary>

* Bagging: Giảm variance bằng cách kết hợp dự đoán từ nhiều mô hình. Giảm Variance
* Boosting: Tăng cường hiệu suất bằng cách kết hợp các mô hình yếu thành mô hình mạnh. Giảm Bias

</details>

<details>

<summary>Sự khác biệt giữa classification và regression là gì? Đưa ra một ví dụ thực tế cho mỗi loại</summary>

* Classification là để dự đoán phân loại. Ví dụ: phân loại ảnh chó mèo
* Regression là để sự đoán giá trị liên tục. Ví dụ: dự đoán giá cổ phiếu

</details>



## 3. Deep Learning

<details>

<summary>Vanishing Gradient và Exploding Gradient là gì? làm sao để ngăn chặn chúng</summary>

* **Vanishing Gradient**: Làm mạng không học được vì gradient quá nhỏ.
* **Exploding Gradient**: Làm mạng không ổn định vì gradient quá lớn.

</details>

<details>

<summary>Giải thích cơ chế hoạt động của Dropout trong Neural Network</summary>

Dropout hoạt động bằng cách tạm thời **loại bỏ (drop)** một số lượng ngẫu nhiên các neurons trong quá trình huấn luyện, giúp mạng học được các đặc trưng mạnh mẽ hơn, giảm thiểu overfitting trong mạng neuron

</details>

<details>

<summary>Sự khác biệt giữa CNN và RNN là gì?</summary>

* **CNN**: Sử dụng khi làm việc với hình ảnh hoặc dữ liệu không gian.
* **RNN**: Sử dụng khi làm việc với chuỗi, thời gian, hoặc ngữ cảnh có tính liên tục.

<img src="../.gitbook/assets/image (47).png" alt="" data-size="original">

</details>



## 4. Deployment

<details>

<summary>Có những cách nào để triển khai mô hình AI?</summary>

* **Cloud**: Khi cần xử lý dữ liệu lớn và mở rộng quy mô.
* **Edge**: Khi xử lý cần độ trễ thấp hoặc môi trường offline.
* **Web**: Khi muốn tiếp cận người dùng rộng rãi qua trình duyệt.
* **API**: Khi cần tích hợp dễ dàng với hệ thống khác.
* **Embedded**: Khi muốn triển khai trên các thiết bị cụ thể.

</details>

<details>

<summary>Làm sao để cập nhật mô hình AI khi có dữ liệu mới xuất hiện</summary>

* Retraining (Huấn luyện lại)&#x20;
* Fine-tuning (Tinh chỉnh mô hình)
* Online Learning (real time - thuật toán SGD)
* Transfer Learning (Học chuyển giao)

</details>



## 5. Situation

<details>

<summary>Bạn sẽ làm gì nếu mô hình AI của bạn không đạt được độ chính xác như bạn mong muốn ?</summary>

1. Đánh giá và phân tích vấn đề

* Phân tích dữ liệu
* Phân tích mô hình

2. Áp dụng các kỹ thuật cải thiển độ chính xác
   1. Cải thiện dữ liệu
   2. Tinh chỉnh mô hình
   3. Thay đổi thuật toán hoặc phương pháp huấn luyện
   4. Cải thiện quy tình huấn luyện
   5. Tăng cường kỹ thuật tối ưu

3) Đánh giá lại mô hình

</details>

<details>

<summary>Bạn làm gì khi dữ liệu của bạn bị <strong>mất cân bằng</strong> ?</summary>

* Resampling
  * Tăng mẫu cho lớp nhỏ
  * Giảm mẫu cho lớp lớn
* Tạo trọng số cho các lớp
* Một số thuật toán được thiết kế để xử lý dữ liệu mất cân bằng:
  * **Tree-based models**: Random Forest, Gradient Boosting thường xử lý mất cân bằng tốt.
  * **Imbalanced-learn**: Một thư viện Python với các thuật toán được tối ưu hóa cho dữ liệu mất cân bằng.

- Data Augmentation tăng cường dữ liệu
- Thay thế hàm mất mát tiêu chuẩn bằng các hàm hỗ trợ dữ liệu mất cân bằng:
  * **Focal Loss**: Tập trung nhiều hơn vào các mẫu khó phân loại.
  * **Weighted Cross-Entropy Loss**: Áp dụng trọng số cho các lớp.

</details>



