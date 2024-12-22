---
description: Giá trị riêng và vector riêng
---

# Eigenvalues và Eigenvector

Eigenvalues và eigenvectors là các khái niệm cực kỳ quan trọng trong đại số tuyến tính và thường được sử dụng trong nhiều ngữ cảnh khoa học và kỹ thuật. Eigenvalue, hay còn gọi là giá trị riêng, là một giá trị vô hướng được liên kết với một ma trận hay toán tử tuyến tính tương ứng. Giá trị này mô tả mức độ mà một eigenvector, hay còn gọi là vector riêng, bị dãn ra hoặc bị co lại khi một toán tử tuyến tính cụ thể được áp dụng lên nó.

Khi một eigenvector được kết hợp với một eigenvalue, nó có đặc điểm là không thay đổi hướng của mình mặc dù có thể thay đổi về độ lớn. Điều này có nghĩa là khi toán tử được áp dụng lên eigenvector, kết quả là một phiên bản được phóng to hoặc thu nhỏ của chính eigenvector đó, không bị xoay hay thay đổi hướng đi.

Eigenvalues và eigenvectors có ứng dụng rộng rãi trong nhiều lĩnh vực. Chẳng hạn như trong việc giải quyết các hệ thống tuyến tính, nơi mà chúng được sử dụng để đơn giản hóa các tính toán. Trong cơ học lượng tử, chúng giúp mô tả các trạng thái lượng tử và quá trình thay đổi trạng thái. Trong xử lý tín hiệu, chúng có vai trò quan trọng trong việc phân tích và nén dữ liệu. Cuối cùng, trong phân tích dữ liệu, eigenvalues và eigenvectors thường được sử dụng trong các kỹ thuật phân tích thành phần chính (PCA) để giảm chiều dữ liệu mà vẫn giữ được những thông tin quan trọng nhất.

***

## 1. Eigenvalues ​​và eigenvector là gì?

### 1.1 Eigenvalues (Eigenvalue)

> Các giá trị riêng là các giá trị vô hướng liên kết với các vector riêng trong phép biến đổi tuyến tính. Từ 'Eigen' có nguồn gốc từ tiếng Đức có nghĩa là 'đặc trưng'.

Trị riêng của một ma trận vuông AAA là một giá trị $$\lambda$$ sao cho tồn tại một vector không bằng 0 $$\mathbf{v}$$, thỏa mãn:&#x20;

$$
A \cdot \mathbf{v} = \lambda \cdot \mathbf{v}
$$

* A: ma trận vuông.
* &#x20;$$\lambda$$ : trị riêng.
* &#x20;$$\mathbf{v}$$: vector riêng tương ứng.

### 1.2 Vector riếng (Eigenventor)

Eigenvectors cho ma trận vuông được định nghĩa là các giá trị vectơ không bằng không mà khi nhân với ma trận vuông sẽ cho ra bội số vô hướng của vectơ đó, nghĩa là chúng ta định nghĩa một eigenvector cho ma trận A là “v” nếu nó thỏa mãn điều kiện, Av = λv

Hệ số nhân λ trong trường hợp trên được gọi là giá trị riêng của ma trận vuông. Chúng ta luôn phải tìm giá trị riêng của ma trận vuông trước khi tìm các vectơ riêng của ma trận.

***

## 2. Công thức tính Eigenvector

Công thức tính eigenvector biểu thị mối quan hệ giữa ma trận vuông ( A ), giá trị riêng ( $$\lambda$$ ), và eigenvector ( $$\mathbf{v}$$ ). Đặc biệt, nó cho ta biết rằng việc nhân ma trận đặc trưng $$(A−\lambda I)$$ với eigenvector ( $$\mathbf{v}$$) sẽ cho kết quả là vector không, từ đó cho phép xác định các giá trị riêng và vectơ riêng của ma trận.

**Eigenvector được tính từ phương trình**:

$$
(A−\lambda I)*\mathbf{v}=0
$$

Trong đó:

* I: Ma trận đơn vị (Identity matrix).
* $$(A - \lambda I)$$: Ma trận đặc trưng.
* $$\mathbf{v}$$: Vector không bằng 0.

Để giải $$\mathbf{v}$$, cần tìm nghiệm của phương trình:

$$
\text{det}(A - \lambda I) = 0
$$

Phương trình này được gọi là **phương trình đặc trưng**, dùng để xác định các giá trị λ(Eigenvalues).

***

## 3. Cách tìm  Eigenvector

Vector riêng của ma trận vuông sau có thể được tính toán dễ dàng bằng các bước dưới đây:

1. **Tính Ma trận đặc trưng**: Tạo ma trận $$(A - \lambda I)$$, trong đó ( A ) là ma trận cần xét và ( I ) là ma trận đơn vị có cùng kích thước.
2. **Giải Phương trình Đặc trưng**: Giải phương trình $$\text{det}(A - \lambda I) = 0$$ để tìm các giá trị riêng ( $$\lambda$$ ) (Eigenvalues).
3. **Tìm Eigenvector ứng với mỗi Eigenvalue**:
   * Thay thế mỗi ( $$\lambda$$ )  đã tìm vào phương trình $$(A - \lambda I)\mathbf{v} = \mathbf{0}$$.
   * Giải hệ phương trình tuyến tính để tìm vector riêng ( $$\mathbf{v}$$ ) không bằng 0 tương ứng với từng ( $$\lambda$$ ) .
4. **Kiểm tra và Xác minh**: Kiểm tra tính đúng đắn của eigenvalues và eigenvectors bằng cách thực hiện phép tính ( $$A\mathbf{v} = \lambda\mathbf{v}$$ ) và xác nhận tính khép kín của chúng.

Thực hiện theo các bước này cung cấp eigenvector liên quan đến ma trận vuông đã cho.

***

## 4. Eigenspace

### Eigenspace là gì?

Eigenspace là không gian con tuyến tính được sinh ra bởi tất cả các eigenvectors tương ứng với một eigenvalue cụ thể của một ma trận. Nói cách khác, nếu ( $$\lambda$$ ) là một giá trị riêng của ma trận ( A ), thì eigenspace của ( $$\lambda$$ ) bao gồm tất cả các vector ( $$\mathbf{v}$$ ) thỏa mãn phương trình $$(A - \lambda I)\mathbf{v} = \mathbf{0}$$. Eigenspace là tập hợp của tất cả các vector riêng cộng với vector zero, tạo thành một không gian vector có chiều bằng số bậc tự do trong hệ phương trình tuyến tính liên quan.

> **Eigenspace l**à tập hợp tất cả các vector riêng tương ứng với một trị riêng λ

Nó là một không gian con của không gian vectơ, được định nghĩa bởi:

$$
\text{Eigenspace}={\mathbf{v} ∈R n  ∣ (\mathbf{A} −\lambda I)⋅\mathbf{v} =0}
$$

### Tính chất của Eigenspace

1. **Tính chất vector con**: Eigenspace là một không gian con của không gian vector ban đầu. Nó bao gồm tất cả các eigenvectors và vector zero.
2. **Tính đóng**: Eigenspace đóng dưới phép cộng và tích với số thực, nghĩa là tổng của hai vector trong eigenspace hoặc một vector trong eigenspace nhân với một số thực vẫn nằm trong eigenspace.
3. **Chiều của eigenspace**: Chiều (dimension) của eigenspace là số vector độc lập tuyến tính trong đó, thường là số bậc tự do của hệ phương trình $$(A - \lambda I)\mathbf{v} = 0$$.
4. **Độc lập với eigenvalue khác**: Các eigenspaces tương ứng với các eigenvalues khác nhau chỉ giao nhau tại vector zero.

### Các bước tìm Eigenspace

1. **Xác định ma trận A**: Bắt đầu với một ma trận vuông A cần tính eigenspace.
2. **Tính trị riêng (eigenvalues)**: Giải phương trình đặc trưng $$\det(\mathbf{A} - \lambda \mathbf{I}) = 0$$ để tìm trị riêng $$\lambda$$.
3. **Giải hệ phương trình**: Với mỗi trị riêng $$\lambda$$, giải hệ phương trình $$(\mathbf{A} - \lambda \mathbf{I}) \mathbf{v} = 0$$ để tìm vector riêng $$\mathbf{v}$$.
4. **Xác định eigenspace**: Tập hợp vector riêng $$\mathbf{v}$$ tìm được lại thành eigenspace tương ứng.

***

## 5.  Ví dụ và ứng dụng

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

# Ma trận
A_torch = torch.tensor([[4, 2],
                        [1, 3]], dtype=torch.float32)

# Tính Eigenvalues và Eigenvectors
eigenvalues_torch, eigenvectors_torch = torch.linalg.eig(A_torch)

print("Eigenvalues:\n", eigenvalues_torch)
print("Eigenvectors:\n", eigenvectors_torch)

```
{% endtab %}

{% tab title="Second Tab" %}
```python
import numpy as np

# Ma trận
A = np.array([[4, 2],
              [1, 3]])

# Tính Eigenvalues và Eigenvectors
eigenvalues, eigenvectors = np.linalg.eig(A)

print("Eigenvalues:\n", eigenvalues)
print("Eigenvectors:\n", eigenvectors)
```
{% endtab %}
{% endtabs %}

#### **Ứng dụng**

1. **Principal Component Analysis (PCA):**
   * Trích xuất trục chính từ ma trận hiệp phương sai.
   * Giảm số chiều dữ liệu.
2. **Stability Analysis:**
   * Dùng Eigenvalues để đánh giá độ ổn định của hệ thống động lực học.
3. **Graph Analysis:**
   * Tính toán Eigenvector của ma trận kề (adjacency matrix) để phân tích cấu trúc đồ thị.
4. **Quantum Mechanics:**
   * Eigenvalues đại diện cho năng lượng của hệ lượng tử.
5. **Machine Learning:**
   * Biểu diễn dữ liệu bằng vector riêng để tăng tốc tính toán.



## 6. Các câu hỏi luyện tập

<details>

<summary>Câu hỏi 1: Eigenvalues và Eigenvectors là gì?</summary>

**Câu trả lời:**

* **Eigenvalues (Giá trị riêng):** Là một hằng số λ sao cho khi nhân một ma trận A với một vector v, kết quả là vector v nhân với λ: $$A \cdot \mathbf{v} = \lambda \cdot \mathbf{v}$$.
* **Eigenvectors (Vector riêng):** Là vector không đổi hướng khi tác động bởi ma trận A, chỉ thay đổi độ lớn theo hệ số λ.

</details>

<details>

<summary>Câu hỏi 2: Làm thế nào để tính Eigenvalues?</summary>

**Câu trả lời:** Để tính Eigenvalues λ, ta giải phương trình đặc trưng: $$\text{det}(A - \lambda I) = 0$$

Trong đó:

* A: Ma trận vuông.
* I: Ma trận đơn vị.
* λ: Nghiệm của phương trình trên, chính là Eigenvalues.

</details>

<details>

<summary>Câu hỏi 3: Eigenspace là gì?</summary>

Eigenspace là tập hợp tất cả các vector riêng tương ứng với một giá trị riêng 𝜆 λ, được định nghĩa bởi:

$$\text{Eigenspace}={\mathbf{v} ∈R n  ∣ (\mathbf{A} −\lambda I)⋅\mathbf{v} =0}$$

Nó là một không gian con của không gian vectơ.

</details>

<details>

<summary>Câu hỏi 4: Eigenvalues có thể là số âm không?</summary>

**Câu trả lời:** Có, Eigenvalues có thể là số âm, số dương, hoặc thậm chí số phức, tùy thuộc vào ma trận A

</details>

<details>

<summary>Câu hỏi 5: Eigenvalues và Eigenvectors được sử dụng ở đâu trong AI?</summary>

**Câu trả lời:**

* **PCA (Phân tích thành phần chính):** Sử dụng Eigenvectors để tìm các trục chính của dữ liệu, giúp giảm số chiều.
* **Graph Analysis:** Tính Eigenvalues để phân tích cấu trúc đồ thị.
* **Stability Analysis:** Dùng Eigenvalues để kiểm tra độ ổn định của hệ thống động lực học.
* **Quantum Mechanics:** Eigenvalues biểu diễn năng lượng của hệ lượng tử.

</details>

<details>

<summary>Câu hỏi luyện tập</summary>

1. **Khám phá khái niệm vector riêng tổng quát và vai trò của chúng trong dạng chuẩn Jordan.**

2) **Chứng minh rằng các ma trận tương tự có cùng giá trị riêng.**

3. **Chỉ ra rằng nếu λ là một giá trị riêng của A, thì λ^k là một giá trị riêng của A^k cho bất kỳ số nguyên dương k.**&#x20;

4) **Chứng minh rằng tích của các giá trị riêng của một ma trận bằng với định thức của nó.**

5. **Chứng minh rằng tổng của các giá trị riêng của một ma trận bằng với vết của nó.**&#x20;

6) **Với ma trận A = \[\[2, -1], \[1, 2]] và giá trị riêng của nó λ = 1 + i, tìm vector riêng tương ứng.**&#x20;

7. **Tìm các giá trị riêng của ma trận A = \[\[0, 1, 0], \[0, 0, 1], \[1, 0, 0]].**&#x20;

8) **Chứng minh rằng các giá trị riêng của ma trận tam giác trên là các phần tử trên đường chéo của nó.**&#x20;

9. **Với một giá trị riêng λ = 2 và vector riêng tương ứng x = \[1, -2]^T, tìm ma trận A.**&#x20;

10) **Đường chéo hóa ma trận A = \[\[2, -1], \[1, 2]].** Tìm các giá trị riêng và vector riêng của ma trận A = \[\[3, 2], \[1, 4]].

</details>



