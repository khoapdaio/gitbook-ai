# Ma trận

## 1. Khái niệm cơ bản

Ma trận là một cấu trúc toán học được biểu diễn dưới dạng bảng chữ nhật gồm các số, ký hiệu hoặc biểu thức, sắp xếp theo hàng và cột. Mỗi phần tử trong ma trận được xác định bằng hai chỉ số - một cho hàng và một cho cột, thường được ký hiệu là $$A_{ij}$$, trong đó i là chỉ số hàng và j là chỉ số cột. Các ma trận có thể là hình vuông - khi số hàng bằng số cột, hoặc hình chữ nhật - khi số hàng khác số cột.

$$
\begin{split}\begin{split}\mathbf{A}=\begin{bmatrix} 
a_{11} & a_{12} & \cdots & a_{1j} \\ 
a_{21} & a_{22} & \cdots & a_{2j} \\ 
\vdots & \vdots & \ddots & \vdots \\ 
a_{i1} & a_{i2} & \cdots & a_{ij} \\ 
\end{bmatrix}.\end{split}\end{split}
$$



Ma trận có ứng dụng rộng rãi trong nhiều lĩnh vực:

* Trong toán học, chúng được dùng để biểu diễn và giải các hệ phương trình tuyến tính, phân tích biến hình học, và nghiên cứu lý thuyết nhóm.
* Trong khoa học máy tính và đồ họa, ma trận được sử dụng để xử lý và biến đổi hình ảnh, điều chỉnh phối cảnh, và hiển thị các đối tượng trong không gian 3 chiều.
* Trong vật lý và kỹ thuật, ma trận đại diện cho các hệ số trong mạng lưới điện, mô tả các trạng thái và chuyển đổi trong lý thuyết lượng tử, và tối ưu hóa mạng truyền thông.

Ma trận cũng đóng vai trò quan trọng trong lĩnh vực trí tuệ nhân tạo và máy học, chẳng hạn qua máy vector hỗ trợ và mạng nơron sâu, nơi ma trận là công cụ chủ đạo trong tính toán và tối ưu hóa.

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

# Tạo ma trận pytorch
vector = torch.tensor([[1, 2], [3, 4]])
print("Ma trận với pytorch:\n", matrix_np)
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np


# Tạo ma trận bằng NumPy
matrix_np = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
print("Ma trận với NumPy:\n", matrix_np)
```


{% endtab %}
{% endtabs %}

***

## 2. Thuộc tính

**Kích thước**: Ma trận có kích thước m x n, trong đó m là số hàng và n là số cột.

{% tabs %}
{% tab title="Torch" %}
<pre class="language-python"><code class="lang-python"><strong>import torch
</strong><strong>
</strong><strong>
</strong><strong>matrix = torch.zeros(3, 4)
</strong>print(matrix.size())  # Output: torch.Size([3, 4])
</code></pre>
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np


matrix = np.zeros((3, 4))
print(matrix.shape)  # Output: (3, 4)
```
{% endtab %}
{% endtabs %}

***

## 3. Các ma trận đặc biệt

**Ma trận đặc biệt** là các dạng ma trận có cấu trúc và tính chất đặc biệt nhất định. Một số loại ma trận đặc biệt phổ biến bao gồm:

* **Ma trận vuông (Square Matrix)**: Ma trận vuông là ma trận có số dòng bằng số cột. Ma trận vuông rất quan trọng vì khi tìm nghiệm cho hệ phương trình, từ ma trận vuông ta có thể chuyển sang ma trận tam giác. Ma trận vuông cũng là ma trận có thể tính được giá trị định thức. Tóm lại ma trận $$A∈R^{m×n}$$ vuông nếu $$m=n$$.
* **Ma trận đơn vị (Identity Matrix)**: Ma trận vuông với các phần tử trên đường chéo chính là 1 và các phần tử còn lại là 0.

$$
\begin{split}\begin{split}\mathbf{A}=
\begin{bmatrix} 
1 & 0 & 0 \\ 
0 & 1 & 0 \\ 
0 & 0 & 1 
\end{bmatrix}
\end{split}\end{split}
$$

* **Ma trận đối xứng (Symmetric Matrix)**: Ma trận vuông mà phần tử tại hàng i, cột j bằng phần tử tại hàng j, cột i.

$$
\begin{split}\begin{split}\mathbf{A}=
\begin{bmatrix} 
1 & 7 & 3 \\ 
7 & 4 & 5 \\ 
3 & 5 & 6 
\end{bmatrix}
\end{split}\end{split}
$$

* **Ma trận không (Zero Matrix)**: Ma trận có tất cả các phần tử đều bằng 0.

$$
\begin{split}\begin{split}\mathbf{A}=
\begin{bmatrix} 
0 & 0 & 0 \\ 
0 & 0 & 0 \\ 
0 & 0 & 0
\end{bmatrix}
\end{split}\end{split}
$$

* **Ma trận đường chéo (Diagonal Matrix)**: Ma trận vuông có tất cả các phần tử ngoài đường chéo chính bằng 0.

$$
\begin{split}\begin{split}\mathbf{A}=
\begin{bmatrix} 
1 & 0 & 0 \\ 
0 & 2 & 0 \\ 
0 & 0 & 3 
\end{bmatrix}
\end{split}\end{split}
$$

* **Ma trận chuyển vị (Transpose Matrix)**: $$B$$ là ma trận chuyển vị của $$A$$ nếu $$b_{ij}=a_{ji}$$ với mọi $$i,j$$. Dễ hiểu hơn, tức là mọi dòng của ma trận $$A$$ sẽ là cột của ma trận $$B$$.

$$
\begin{split}\begin{split}\mathbf{A}=
\begin{bmatrix} 
2 & 3 & 6 \\ 
1 & 4 & 5  
\end{bmatrix}
\end{split}\end{split},\begin{split}\begin{split}\mathbf{B}=
\begin{bmatrix} 
1 & 2 \\ 
4 & 3 \\ 
5 & 6  
\end{bmatrix}
\end{split}\end{split}
$$

Các ma trận đặc biệt thường được sử dụng để đơn giản hóa phép tính và phân tích trong toán học.

## 4. Các phép tính

### 4.1 Các phép toán cơ bản

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch


A = torch.tensor([[1, 2], [3, 4]])
B = torch.tensor([[5, 6], [7, 8]])

# Phép cộng ma trận
print("Cộng ma trận A,B: \n", A + B)
# Phép trừ ma trận
print("Trừ ma trận A,B: \n", A - B)
# Phép nhân ma trận
print("Phép nhân ma trận A,B: \n", torch.mm(A,B) )# hoặc A @ B
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np

A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

# Phép cộng ma trận
print("Cộng ma trận A,B: \n", A + B)
# Phép trừ ma trận
print("Trừ ma trận A,B: \n", A - B)
# Phép nhân ma trận
print("Phép nhân ma trận A,B: \n", np.dot(A,B) )# hoặc A @ B
```
{% endtab %}
{% endtabs %}

### 4.2 Chuyển vị ma trận ( Transpose):

Chuyển vị của một ma trận là ma trận mới tạo ra bằng cách đổi chỗ các hàng và cột của ma trận gốc. Ký hiệu thường dùng cho chuyển vị là (A^T).

$$
\begin{split}\begin{split}\mathbf{A}=
\begin{bmatrix} 
2 & 3 & 6 \\ 
1 & 4 & 5  
\end{bmatrix}
\end{split}\end{split},\begin{split}\begin{split}\mathbf{A^T}=
\begin{bmatrix} 
1 & 2 \\ 
4 & 3 \\ 
5 & 6  
\end{bmatrix}
\end{split}\end{split}
$$



```python
# Numpy
A_transpose = A.T

# PyTorch
A_torch_transpose = A_torch.t()
```

### 4.3 Định thức và ma trạn nghịch đảo

**Định thức** của một ma trận là một số vô hướng có nguồn gốc từ các phần tử của ma trận, thường được sử dụng để kiểm tra xem ma trận có thể nghịch đảo được không. Nếu định thức khác 0, ma trận đó có thể có ma trận nghịch đảo.

$$
\begin{bmatrix} a & b \cr c & d \end{bmatrix},\text{det}(A) = ad - bc
$$

**Ma trận nghịch đảo** là ma trận mà khi nhân với ma trận gốc sẽ cho ra ma trận đơn vị. Chỉ các ma trận vuông có định thức khác 0 mới có ma trận nghịch đảo.

$$
A= \begin{bmatrix} a & b \cr c & d \end{bmatrix}
$$

$$
A^{-1} = \frac{1}{ad - bc} \begin{bmatrix} d & -b \cr -c & a \end{bmatrix}
$$

{% tabs %}
{% tab title="Pytorch" %}
<pre class="language-python"><code class="lang-python">import torch
<strong>
</strong><strong>det_A_torch = torch.det(A_torch.float())
</strong>inv_A_torch = torch.inverse(A_torch.float())
print("PyTorch Determinant:\n", det_A_torch)
print("PyTorch Inverse:\n", inv_A_torch)
</code></pre>
{% endtab %}

{% tab title="Numpy" %}
<pre class="language-python"><code class="lang-python">import numpy as np

<strong>det_A = np.linalg.det(A)
</strong>inv_A = np.linalg.inv(A)
print("NumPy Determinant:\n", det_A)
print("NumPy Inverse:\n", inv_A)
</code></pre>


{% endtab %}
{% endtabs %}

### 4.4 Phân rã ma trận( Matrix Decomposition)

#### 4.4.1 Phân ra giá trị kỳ dị

Phân rã giá trị kỳ dị (Singular Value Decomposition - SVD) là một phương pháp phân tách một ma trận thành ba ma trận thành phần. Cụ thể, một ma trận ( A ) có thể được phân tách thành ba ma trận ( U ), ( S ), và ( $$V^T$$ ), sao cho ( A = U S $$V^T$$ ). Trong đó:

* ( U ) và ( $$V^T$$) là các ma trận trực giao (orthogonal matrices).
* ( S ) là một ma trận đường chéo chứa các giá trị kỳ dị của ( A ).

SVD thường được sử dụng trong phân tích dữ liệu, giảm chiều không gian, và xử lý tín hiệu số.

```python
# NumPy
U, S, VT = np.linalg.svd(A)
print("NumPy SVD:\nU:\n", U, "\nS:\n", S, "\nV^T:\n", VT)

# PyTorch
U_torch, S_torch, V_torch = torch.svd(A_torch.float())
print("\nPyTorch SVD:\nU:\n", U_torch, "\nS:\n", S_torch, "\nV^T:\n", V_torch)

```



#### 4.4.2 Phân rã Eigen

#### Phân Rã Eigen

Phân rã eigen, hay còn gọi là phân tích giá trị riêng, là một kỹ thuật toán học chỉ ra cách một ma trận có thể được biểu diễn bằng các giá trị riêng (eigenvalues) và vector riêng (eigenvectors). Đối với một ma trận vuông ( A ), quá trình này được biểu diễn dưới dạng:

$$
A \cdot \mathbf{v} = \lambda \cdot \mathbf{v}
$$

Trong đó:

* ( $$\mathbf{v}$$ ) là một vector riêng liên quan đến ma trận ( A ).
* ( $$\lambda$$ ) là giá trị riêng tương ứng với vector ( $$\mathbf{v}$$ ).

Phân rã eigen giúp ta hiểu sâu hơn cấu trúc của ma trận và được ứng dụng rộng rãi trong các lĩnh vực như cơ học lượng tử, xử lý tín hiệu, và học máy. Dưới đây là cách thực hiện phân rã eigen bằng NumPy và PyTorch:

```python
# NumPy
eigvals, eigvecs = np.linalg.eig(A)
print("NumPy Eigenvalues:\n", eigvals)
print("NumPy Eigenvectors:\n", eigvecs)

# PyTorch
eigvals_torch, eigvecs_torch = torch.eig(A_torch.float(), eigenvectors=True)
print("\nPyTorch Eigenvalues:\n", eigvals_torch)
print("PyTorch Eigenvectors:\n", eigvecs_torch)
```

Phương pháp này giúp trích xuất các yếu tố tiềm năng từ dữ liệu và cung cấp một công cụ mạnh mẽ để phân tích ma trận.

## 5. Truy cập thành phần

Chúng ta có thể truy cập vào các thành phần của ma trận $$A$$ dựa theo các chỉ số slice index. Chúng ta có thể tổng hợp kiến thức về truy cập thành phần trong bản sau:

| Cú pháp | Mô tả                                                                                     |
| ------- | ----------------------------------------------------------------------------------------- |
| :n      | lấy n index đầu tiên từ \[0, 1, …, n-1]                                                   |
| -n:     | lấy n index cuối cùng từ \[len-n, …, len-1]                                               |
| i:j     | lấy các index từ \[i, i+1, …, j-1]                                                        |
| ::2     | lấy các index chẵn liên tiếp \[0, 2, 4 …, int(len/2)\*2]                                  |
| ::k     | lấy các index cách đều và chia hết cho k một cách liên tiếp \[0, k, 2k, …, int(len/k)\*k] |
| :       | lấy toàn bộ index                                                                         |



{% tabs %}
{% tab title="Pytorch" %}
<pre class="language-python"><code class="lang-python">import torch
A = torch.tensor([[1, 2, 3], 
                  [3, 2, 1],
                  [4, 2, 2]])


# Truy cập ma trận con từ 2 dòng đầu tiên và 2 cột đầu tiên.
<strong>print(A[:2, :2])
</strong>
# Truy cập ma trận con từ 2 dòng cuối cùng và 2 cột đầu tiên
print(A[-2:, :2])

# Truy cập véc tơ con từ dòng thứ 2 và 2 cột cuối cùng.
print(A[2, -2:]))

# Hoặc
print(A[2:3, -2:][0])

# Truy cập ma trận có các dòng chẵn
<strong>print(A[::2, :])
</strong>
# Truy cập một index cụ thể , ví dụ dòng 0, 2 của ma trận
print(A.index_select(0, torch.tensor([0, 2])))
# Trong công thức trên 0 là chiều mà ta sẽ lấy,
# tensor([0, 2]) là các index ta sẽ lấy từ chiều 0.
</code></pre>
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np
A = np.array([[1, 2, 3], 
              [3, 2, 1],
              [4, 2, 2]])

# Truy cập ma trận con từ 2 dòng đầu tiên và 2 cột đầu tiên.
print(A[:2, :2])

# Truy cập ma trận con từ 2 dòng cuối cùng và 2 cột đầu tiên
print(A[-2:, :2])

# Truy cập véc tơ con từ dòng thứ 2 và 2 cột cuối cùng.
print(A[2, -2:]))

# Hoặc
print(A[2:3, -2:][0])

# Truy cập ma trận có các dòng chẵn
print(A[::2, :])

# Truy cập một index cụ thể , ví dụ dòng 0, 2 của ma trận
print(A[[0, 2], :])
```
{% endtab %}
{% endtabs %}



