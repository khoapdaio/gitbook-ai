# Phép biến đổi tuyến tính

## 1. Khái niệm cơ bản

Phép biến đổi tuyến tính là ánh xạ từ một không gian vector sang không gian vector khác, duy trì các tính chất của phép cộng và phép nhân với một số thực:

$$
T(a⋅v+b⋅u)=a⋅T(v)+b⋅T(u)
$$

với 𝑎 , 𝑏 là hằng số, 𝑣 , 𝑢  là vector.

**Ứng dụng**:

* Biểu diễn các phép quay, co dãn, phản chiếu, và chuyển vị trong không gian.
* Giảm số chiều trong PCA hoặc embedding.
* Biến đổi dữ liệu đầu vào trong các mô hình học máy.

***

## 2. Các phép biến đổi cơ bản

### 2.1 Phép quay (Rotation)

**Phép quay (Rotation)** là một phép biến đổi hình học xoay các điểm quanh một điểm gốc hoặc một trục cố định, với một góc quay xác định. Trong không gian hai chiều, phép quay quanh gốc tọa độ được biểu diễn bằng ma trận xoay, chuyển đổi tọa độ của một vector bằng công thức toán học. Phép quay bảo toàn khoảng cách giữa các điểm và hình dáng của hình học ban đầu.

> Phép quay (Rotation) là một phép biến đổi vector trong không gian bằng cách quay nó một góc 𝜃 θ quanh gốc tọa độ.

**Ma trận quay** trong 2D:

$$
A=\begin{bmatrix}cos(\theta)&-sin(\theta)\cr sin(\theta)&cos(\theta)\end{bmatrix}
$$

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

theta_torch = torch.tensor(np.pi / 4)
rotation_matrix_torch = torch.tensor([[torch.cos(theta_torch), -torch.sin(theta_torch)],
                                       [torch.sin(theta_torch),  torch.cos(theta_torch)]])
                                       
vector_torch = torch.tensor([1, 0], dtype=torch.float32)
rotated_vector_torch = torch.matmul(rotation_matrix_torch, vector_torch)

print("\nPyTorch Rotated Vector:\n", rotated_vector_torch)
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np

theta = np.pi / 4  # 45 degrees
rotation_matrix = np.array([[np.cos(theta), -np.sin(theta)],
                            [np.sin(theta),  np.cos(theta)]])
vector = np.array([1, 0])
rotated_vector = np.dot(rotation_matrix, vector)
print("NumPy Rotated Vector:\n", rotated_vector)
```
{% endtab %}
{% endtabs %}

### 2.2 Phép co dãn (Scaling)

### 2.2 Phép co dãn (Scaling)

Phép co dãn (Scaling) là một phép biến đổi hình học thay đổi kích thước của một vector hoặc hình trong không gian mà không làm thay đổi hình dạng của nó. Trong không gian 2D, phép co dãn có thể được thực hiện bằng cách nhân các tọa độ của các điểm với các hệ số tỷ lệ trên các trục tọa độ.

> &#x20;Phép co dãn là phép thay đổi kích thước của vector theo một tỉ lệ 𝑠 s

**Ma trận co dãn**

$$
A=\begin{bmatrix}S_x&0\cr 0&S_y\end{bmatrix}
$$

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch


scaling_matrix_torch = torch.tensor([[2, 0], [0, 3]])
vector_torch = torch.tensor([1, 1], dtype=torch.float32)
scaled_vector_torch = torch.matmul(scaling_matrix_torch, vector_torch)

print("\nPyTorch Scaled Vector:\n", scaled_vector_torch)
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np

scaling_matrix = np.array([[2, 0], [0, 3]])  # Scale by 2 in x, 3 in y
vector = np.array([1, 1])
scaled_vector = np.dot(scaling_matrix, vector)

print("NumPy Scaled Vector:\n", scaled_vector)
```
{% endtab %}
{% endtabs %}

### 2.3 Phép phản chiếu (Reflection)

Phép phản chiếu là phép biến đổi ánh xạ mỗi điểm của đối tượng đến điểm đối xứng qua trục hoặc mặt phẳng.

> Phản chiếu vector qua một trục hoặc mặt phẳng.

#### Ma trận phản chiếu qua trục x:

$$
R=\begin{bmatrix}1&0\cr 0&-1\end{bmatrix}
$$

#### Ma trận phản chiếu qua trục y:

$$
R=\begin{bmatrix}-1&0\cr 0&1\end{bmatrix}
$$

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch


reflection_matrix_x = torch.tensor([[1, 0], [0, -1]])
vector = torch.tensor([1, 1], dtype=torch.float32)
reflected_vector = torch.matmul(reflection_matrix_x, vector)

print(reflected_vector)
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np
reflection_matrix_y = np.array([[-1, 0], [0, 1]])
vector = np.array([1, 1])
reflected_vector = np.dot(reflection_matrix_y, vector)
print(reflected_vector)
```
{% endtab %}
{% endtabs %}

### 2.4 Phép chuyển vị

#### Phép chuyển vị

Phép chuyển vị của một ma trận là thao tác đảo đổi hàng thành cột và ngược lại. Đối với một ma trận $A$ có kích thước $m \times n$, ma trận chuyển vị $A^T$ sẽ có kích thước $n \times m$, với phần tử tại hàng $i$ và cột $j$ của $A$ được chuyển thành phần tử tại hàng $j$ và cột $i$ của $A^T$. Phép chuyển vị thường được sử dụng để biến đổi không gian và giải quyết các bài toán tuyến tính.

{% tabs %}
{% tab title="Pytorch" %}
<pre class="language-python"><code class="lang-python"><strong>import torch
</strong><strong>
</strong><strong>translation_matrix_torch = torch.tensor([[1, 0, 2],
</strong>                                         [0, 1, 3],
                                         [0, 0, 1]])
vector_torch = torch.tensor([1, 1, 1], dtype=torch.float32)
translated_vector_torch = torch.matmul(translation_matrix_torch, vector_torch)

print("PyTorch Translated Vector:\n", translated_vector_torch)
</code></pre>
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np

translation_matrix = np.array([[1, 0, 2],  # Translate by (2, 3)
                                [0, 1, 3],
                                [0, 0, 1]])
vector = np.array([1, 1, 1])  # Homogeneous coordinates
translated_vector = np.dot(translation_matrix, vector)

print("NumPy Translated Vector:\n", translated_vector)
```
{% endtab %}
{% endtabs %}

***

## 3. Tổ hợp các phép biến đổi

Tổ hợp các phép biến đổi là quá trình áp dụng nhiều phép biến đổi liên tiếp trên một đối tượng hoặc không gian. Trong toán học và khoa học máy tính, các phép biến đổi thường được biểu diễn bằng ma trận và tổ hợp các phép biến đổi là nhân các ma trận tương ứng.

> Kết hợp các phép biến đổi bằng cách nhân các ma trận tương ứng.

#### Ví Dụ Các Tổ Hợp Thường Dùng

1. **Phép Tịnh Tiến và Phép Quay**: Tịnh tiến một điểm trong không gian rồi quay nó quanh một trục cố định.
2. **Phép Co Giãn và Phép Tịnh Tiến**: Co giãn một hình theo một trục nhất định, sau đó di chuyển nó đến một vị trí khác.
3. **Phép Đối Xứng và Phép Quay**: Đối xứng một hình qua một trục trước khi quay nó quanh một điểm cố định.

Việc kết hợp các phép biến đổi này cho phép linh hoạt trong việc điều chỉnh và thể hiện các đối tượng trong không gian khác nhau, đặc biệt quan trọng trong lĩnh vực đồ họa máy tính và thị giác máy.

## 4. Ma trận Jacob và biến đổi không gian

Ma trận Jacob, hay còn gọi là Jacobian, là một ma trận chứa các đạo hàm riêng phần của một hàm nhiều biến. Trong toán học, ma trận Jacob là công cụ quan trọng để phân tích và giải quyết các bài toán liên quan đến đạo hàm trong không gian nhiều chiều. Nó đóng vai trò chủ chốt trong việc tính toán tốc độ thay đổi của một hàm khi các biến đầu vào thay đổi.

Công thức tổng quát của ma trận Jacob cho một hàm vector $$\mathbf{F}: \mathbb{R}^n \to \mathbb{R}^m$$ , với $$\mathbf{F}(x_1, x_2, ..., x_n) = [f_1(x_1, x_2, ..., x_n), f_2(x_1, x_2, ..., x_n), ..., f_m(x_1, x_2, ..., x_n)]$$ \
được biểu diễn như sau:

$$
J = \begin{bmatrix} \frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & \cdots & \frac{\partial f_1}{\partial x_n} \ \frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & \cdots & \frac{\partial f_2}{\partial x_n} \ \vdots & \vdots & \ddots & \vdots \ \frac{\partial f_m}{\partial x_1} & \frac{\partial f_m}{\partial x_2} & \cdots & \frac{\partial f_m}{\partial x_n} \end{bmatrix}
$$

{% tabs %}
{% tab title="Pytorch" %}
```python
import pytorch

# PyTorch: Tính Jacobi
inputs_torch = torch.tensor([1.0, 2.0], requires_grad=True)
output = torch.tensor([inputs_torch[0]**2 + inputs_torch[1], inputs_torch[1]**2 + inputs_torch[0]])
jacobi_matrix_torch = torch.autograd.functional.jacobian(lambda x: torch.tensor([x[0]**2 + x[1], x[1]**2 + x[0]]), inputs_torch)

print("\nPyTorch Jacobi Matrix:\n", jacobi_matrix_torch)
```
{% endtab %}

{% tab title="Second Tab" %}
```python
import numpy as np

def jacobian(func, inputs):
    n = len(inputs)
    jac = np.zeros((n, n))
    epsilon = 1e-5
    for i in range(n):
        perturbed = inputs.copy()
        perturbed[i] += epsilon
        jac[:, i] = (func(perturbed) - func(inputs)) / epsilon
    return jac

func = lambda x: np.array([x[0]**2 + x[1], x[1]**2 + x[0]])
inputs = np.array([1.0, 2.0])
jacobi_matrix = jacobian(func, inputs)
print("NumPy Jacobi Matrix:\n", jacobi_matrix)
```


{% endtab %}
{% endtabs %}



Ma trận Jacob rất quan trọng trong nhiều lĩnh vực ứng dụng, bao gồm tối ưu hóa, phân tích độ ổn định và trong các phương pháp giải hệ phương trình phi tuyến tính.

















