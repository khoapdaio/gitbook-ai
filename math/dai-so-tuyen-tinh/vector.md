# Vector

## 1. **Khái niệm cơ bản về vector**

Vector là một đối tượng toán học biểu diễn các giá trị có hướng trong không gian n-chiều. Nó thường được coi là một mảng có thứ tự chứa các số thực hoặc số phức, và ứng dụng trong nhiều lĩnh vực như hình học, vật lý, và học máy.

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch 

# Tạo vector với Pandas
vector_torch = torch.tensor([1, 2, 3])
print("Vector Pytorch:\n", vector_torch )
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np

# Tạo vector với NumPy
vector_np = np.array([1, 2, 3])
print("Vector NumPy:", vector_np)
```
{% endtab %}
{% endtabs %}

***

## 2.  Các c**huẩn (Norm) của vector**

Chuẩn (norm) của vector là phép đo để đánh giá độ dài hay kích thước của vector. Các chuẩn phổ biến gồm chuẩn Euclidean và chuẩn Manhattan, dùng để đo khoảng cách và độ lớn trong không gian.

* **Chuẩn Euclidean**: $$∥v∥ _2 ​  =  \sqrt{\sum v^2_i}$$
* **Chuẩn Manhattan**: $$∥v∥ _1 ​  =  \sum |v_i|$$

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

vector_torch = torch.tensor([1.0, 2.0, 3.0])

# Chuẩn Euclidean
euclidean_norm_torch = torch.norm(vector_torch)
print("Chuẩn Euclidean PyTorch:", euclidean_norm_torch)

# Chuẩn Manhattan
manhattan_norm_torch = torch.norm(vector_torch, p=1)
print("Chuẩn Manhattan PyTorch:", manhattan_norm_torch)
```
{% endtab %}

{% tab title="Numpy" %}
<pre class="language-python"><code class="lang-python"><strong>import numpy as np
</strong>from numpy.linalg import norm

# Chuẩn Euclidean
euclidean_norm = norm(vector_np)
print("Chuẩn Euclidean numpy:", euclidean_norm)

# Chuẩn Manhattan
manhattan_norm = norm(vector_np, ord=1)
print("Chuẩn Manhattan numpy:", manhattan_norm)
</code></pre>
{% endtab %}
{% endtabs %}

***

## 3. Thuộc tính

Trong vector có hai thành phần chính là độ dài và định dạng của vector. Còn để phục vụ thống kê thì sẽ có thêm các hàm cơ bản như:&#x20;

* Sum: Tính tổng các giá trị có trong vector
* Mean: Tính trung bình tổng các giá trị có trong vector
* Min: Trả về số có giá trị nhỏ nhất
* Max: Trả về số có giá trị lớn nhất

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

vector_torch = torch.tensor([1.0, 2.0, 3.0])

# Độ dài
print("length of vector: ", vector_torch.size()) # or len(x)

# Định dạng của véc tơ
print("vector type: ", vector_torch.dtype)

# Tổng của các phần tử 
print("sum of vector: ", vector_torch.sum().item())

# Trung bình các phần tử
print("mean of vector: ", vector_torch.mean().item())

# Giá trị nhỏ nhất
print("min of vector: ", vector_torch.min().item())

# Giá trị lớn nhất
print("max of vector: ", vector_torch.max().item())
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np


vector_numpy =  np.array([1, 2, 3, 4, 5])

# Độ dài
print("length of vector: ", vector_numpy.shape) # or len(x)

# Định dạng của véc tơ
print("vector type: ", vector_numpy.dtype)

# Tổng của các phần tử 
print("sum of vector: ", vector_numpy.sum())

# Trung bình các phần tử
print("mean of vector: ", vector_numpy.mean())

# Giá trị nhỏ nhất
print("min of vector: ", vector_numpy.min())

# Giá trị lớn nhất
print("max of vector: ", vector_numpy.max())
```
{% endtab %}
{% endtabs %}

***

## 4. Phép tính trên vector

Chúng ta có thể thực hiện các phép tính cộng trừ nhân giữa hai vector, giữa vector với một số vô hướng

> **Lưu ý:  vector phải có cùng độ dài**

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

x = torch.tensor([2, 3, 4.5, 6.8, 6.9])
y = torch.tensor([1.2, 3.2, 5.2, 1.6, 6.7])

# Phép tính giữa vector với vector
print("x + y: ", x + y)
print("x - y: ", x - y)
print("x * y: ", x * y)

# Phép tính giữa vector và một số vô hướng
print("x + 5: ", x + 5)
print("x - 5: ", x - 5)
print("x * 5: ", x * 5)
```


{% endtab %}

{% tab title="Numpy" %}
<pre class="language-python"><code class="lang-python"><strong>import numpy as np
</strong><strong>
</strong><strong>x = np.array([2, 3, 4.5, 6.8, 6.9])
</strong>y = np.array([1.2, 3.2, 5.2, 1.6, 6.7])

# Phép tính giữa vector với vector
print("x + y: ", x + y)
print("x - y: ", x - y)
print("x * y: ", x * y)

# Phép tính giữa vector và một số vô hướng
print("x + 5: ", x + 5)
print("x - 5: ", x - 5)
print("x * 5: ", x * 5)
</code></pre>


{% endtab %}
{% endtabs %}



### 4.1 **Tích vô hướng (Dot Product)**

Tích vô hướng (Dot Product) là một phép toán đại số giữa hai vector có cùng kích thước. Kết quả của phép nhân này là một số vô hướng, được tính bằng cách nhân các phần tử tương ứng của hai vector và sau đó lấy tổng kết quả của các tích đó. Tính chất chính của tích vô hướng bao gồm tính giao hoán và phân phối. Dưới đây là công thức cho tích vô hướng:

$$
\mathbf{u} \cdot \mathbf{v} = u_1v_1 + u_2v_2 + \dots + u_nv_n = \sum_{i=1}^{n} u_i v_i
$$



{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

vector_torch_2 = torch.tensor([4, 5, 6])

dot_product_torch = torch.dot(vector_torch, vector_torch_2)

print("Tích vô hướng PyTorch:", dot_product_torch.item())
```
{% endtab %}

{% tab title="Numpy" %}
<pre class="language-python"><code class="lang-python">import numpy as np
<strong>
</strong><strong>length_np = np.linalg.norm(vector_np)
</strong><strong>
</strong>print("Độ dài vector NumPy:", length_np)
</code></pre>
{% endtab %}
{% endtabs %}

***

### 4.2 **Tích có hướng (Cross Product)**

Tích có hướng, hay còn gọi là tích chéo (cross product), là một phép toán giữa hai vector trong không gian ba chiều. Kết quả của phép tính này là một vector mới vuông góc với cả hai vector ban đầu và có độ lớn bằng diện tích của hình bình hành tạo bởi hai vector đó.

Tích có hướng áp dụng cho vector trong không gian 3 chiều: $$\mathbf{u} \times \mathbf{v}$$ .

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

cross_product_torch = torch.cross(vector_torch, vector_torch_2)

print("Tích có hướng PyTorch:", cross_product_torch)
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np

cross_product_np = np.cross(vector_np, vector_np_2)

print("Tích có hướng NumPy:", cross_product_np)
```
{% endtab %}
{% endtabs %}

***

### 4.3 So sánh các phần tử&#x20;

So sánh các phần tử trong vector là phép toán xác định mối quan hệ giữa các phần tử của một hoặc hai vector, bằng cách so sánh với số vô hướng hoặc so sánh cặp phần tử tương ứng. Kết quả là một vector boolean biểu diễn kết quả từng phép so sánh.

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

vector_a = torch.tensor([1, 2, 9, 4, 6, 8])
vector_b = torch.tensor([3, 5, 4, 1, 2, 6])


print("So sánh vector với số vô hướng:",  vector_a > 3)
print("So sánh vector với vector:",  torch.eq(vector_a,vector_) )
```
{% endtab %}

{% tab title="Numpy" %}
<pre class="language-python"><code class="lang-python"><strong>import numpy as np
</strong><strong>
</strong>vector_a = np.array([1, 2, 9, 4, 6, 8])
vector_b = np.array([3, 5, 4, 1, 2, 6])
<strong>
</strong><strong>
</strong>print("So sánh vector với số vô hướng:",  vector_a > 3)
print("So sánh vector với vector:",  vector_a > vector_b )
print("So sánh vector với vector:",  np.equal(vector_a , vector_b ) )

 
</code></pre>


{% endtab %}
{% endtabs %}





### 4.4 **Góc giữa hai vector**

Góc giữa hai vector θ được tính bởi: $$\cos(\theta) = \frac{\mathbf{u} \cdot \mathbf{v}}{\|\mathbf{u}\| \|\mathbf{v}\|}$$.

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch
import torch.nn.functional as F

# Định nghĩa hai vector
vector_a = torch.tensor([1.0, 2.0, 3.0])
vector_b = torch.tensor([4.0, 5.0, 6.0])

# Tính cosine của góc giữa hai vector
cosine_angle = F.cosine_similarity(vector_a, vector_b, dim=0)

# Chuyển cosine sang góc (radian)
angle_rad = torch.acos(cosine_angle)

# In kết quả
print(f"Góc giữa hai vector (radian): {angle_rad.item()}")
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np

# Tính toán cosin của góc giữa hai vector
cos_theta = np.dot(vector_u, vector_v) / (np.linalg.norm(vector_u) * np.linalg.norm(vector_v))

# Tính toán góc giữa hai vector (đơn vị radian)
theta = np.arccos(cos_theta)

print("Góc giữa hai vector (radian):", theta)
```
{% endtab %}
{% endtabs %}



***

### 4.5 **Chiếu vector**

Chiều của một vector là hướng mà nó chỉ trong không gian. Trong hệ tọa độ, chiều được xác định bởi gốc tọa độ và tọa độ đầu mút của vector. Điều này rất quan trọng khi thao tác với các phép toán vector như phép chiếu và tìm góc giữa hai vector.

Chiếu vector $$\mathbf{u}$$ lên vector $$\mathbf{v}$$: $$\text{proj}_{\mathbf{v}} \mathbf{u} = \frac{\mathbf{u} \cdot \mathbf{v}}{\|\mathbf{v}\|^2} \mathbf{v}$$.

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

# Define the vectors as a PyTorch tensor
vectors = torch.tensor([[1, 2, 3], [4, 5, 6], [7, 8, 10]], dtype=torch.float)

# Calculate the rank of the matrix created by the vectors
rank = torch.linalg.matrix_rank(vectors)

if rank.item() == vectors.size(0):
    print("Các vector độc lập tuyến tính")
else:
    print("Các vector phụ thuộc tuyến tính")
```
{% endtab %}

{% tab title="Numpy" %}
```python
# Importing the numpy library for numerical operations
import numpy as np


# Calculate the projection of vector_u onto vector_v
projection = (np.dot(vector_u, vector_v) / norm(vector_v)**2) * vector_v

# Output the result of the projection
print("Vector chiếu:", projection)
```
{% endtab %}
{% endtabs %}



***

## 5. **Vector đơn vị**

Một vector đơn vị là một vector có độ dài bằng 1. Để biến đổi một vector bất kỳ thành vector đơn vị, ta chia mọi thành phần của vector đó cho độ dài của nó. Công thức này giúp trong việc chuẩn hóa vector để giữ nguyên hướng nhưng độ dài bằng 1.\


$$
\mathbf{u}_{unit} = \frac{\mathbf{u}}{\|\mathbf{u}\|}
$$

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

# Tạo vector đơn vị (unit vector)
vec = torch.tensor([1.0, 0.0, 0.0])

# Kiểm tra độ dài của vector
length = torch.norm(vec)

if length == 1:
    print("Đây là một vector đơn vị")
else:
    print("Đây không phải là một vector đơn vị")
```
{% endtab %}

{% tab title="Numpy" %}
```python
import numpy as np

# Define a vector
vector = np.array([3, 4])

# Calculate the magnitude of the vector
magnitude = np.linalg.norm(vector)

# Create the unit vector
unit_vector = vector / magnitude

print("Unit vector:", unit_vector)
```
{% endtab %}
{% endtabs %}

***

## 6. **Linearly Independent Vectors (Độc lập tuyến tính)**

Một tập vector là độc lập tuyến tính nếu không vector nào có thể biểu diễn dưới dạng tổ hợp tuyến tính của các vector khác.

**Kiểm tra độc lập tuyến tính bằng Python**:

{% tabs %}
{% tab title="Pytorch" %}
```python
import torch

# Tạo ma trận từ tập vector
vectors = torch.tensor([[1, 2, 3], [4, 5, 6], [7, 8, 10]], dtype=torch.float)

# Tính hạng của ma trận
rank = torch.linalg.matrix_rank(vectors)

if rank == len(vectors):
    print("Các vector độc lập tuyến tính")
else:
    print("Các vector phụ thuộc tuyến tính")
```
{% endtab %}

{% tab title="Second Tab" %}
```python
import numpy as np
from numpy.linalg import matrix_rank

# Tạo ma trận từ tập vector
vectors = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 10]])
rank = matrix_rank(vectors)

if rank == len(vectors):
    print("Các vector độc lập tuyến tính")
else:
    print("Các vector phụ thuộc tuyến tính")
```
{% endtab %}
{% endtabs %}

