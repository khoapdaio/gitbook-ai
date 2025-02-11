# RNN

## 1. Overview

### 1.1 Kiến trúc truyền thông

Các mạng Neuron hồi quy, còn được biết đến như là RNNs, là một lớp của mạng neural cho phép đầu ra được sử dụng như đầu vào trong khi có các trạng thái ẩn. RNNs được thiết kế để xử lý dữ liệu tuần tự như chuỗi thời gian, văn bản, âm thanh và video Thông thường như sau:

<figure><img src="../.gitbook/assets/Sequentail.gif" alt=""><figcaption></figcaption></figure>



<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Tại mỗi bước t, giá trị kích hoạt $$a^{<t>}$$ và đầu ra $$y^{<t>}$$ được biểu diễn như sau:

$$
a^{<t>}= g_1(W_{aa}a^{t-1}+W_{ax}x^{<t>}+b_a)\text{ và }y^{<t>}= g_2(W_{ya}a^{<t>}+b_y)
$$

với $$W_{ax},W_{aa},W_{ya},b_a,b_y$$ là các hệ số được chia sẻ tạm thời và $$g_1,g_2$$ là các hàm kích hoạt.

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

Ưu nhược điểm của một kiến trúc RNN thông thường được tổng kết ở bảng dưới đây:

<table data-full-width="true"><thead><tr><th>Ưu điểm </th><th>Nhược điểm</th></tr></thead><tbody><tr><td><ul><li>Khả năng xử lí đầu vào với bất kì độ dài nào</li><li>Kích cở mô hình không tăng theo kích cỡ đầu vào </li><li>Quá trình tính toán sử dụng các thông tin cũ</li><li>Trọng số được chia sẽ trong suốt thời gian </li></ul></td><td><ul><li>Tính toán chậm</li><li>Khó để truy cập các thông tin từ một khoảng thời gian dài trước đây</li><li>Không thể xem xét bất kì đầu vào sau này nào cho trạng thái hiện tại</li></ul></td></tr></tbody></table>

### 1.2 Ứng dụng của RNNs

Các mô hình RNN hầu như được sử dụng trong lĩnh vực xử lí ngôn ngữ tự nhiên và ghi nhận tiếng nói. Các ứng dụng khác được tổng kết trong bảng dưới đây:

<table data-full-width="false"><thead><tr><th width="168">Các loại RNN</th><th width="372">Hình minh họa</th><th>Ví dụ</th></tr></thead><tbody><tr><td>Một - Một<br><span class="math">T_x=T_y=1</span></td><td><img src="../.gitbook/assets/image (6).png" alt="" data-size="original"></td><td>Mạng neural truyền thống</td></tr><tr><td>Một - Nhiều<br><span class="math">T_x=1,T_y>1</span></td><td><img src="../.gitbook/assets/image (7).png" alt="" data-size="original"></td><td>Sinh nhạc</td></tr><tr><td>Nhiều - Một<br><span class="math">T_x>1,T_y=1</span></td><td><img src="../.gitbook/assets/image (13).png" alt="" data-size="original"></td><td>Phân loại ý kiến</td></tr><tr><td>Nhiều - Nhiều<br><span class="math">T_x=T_y</span></td><td><img src="../.gitbook/assets/image (9).png" alt="" data-size="original"></td><td>Ghi nhận thực thể tên</td></tr><tr><td>Nhiều - Nhiều<br><span class="math">T_x\ne T_y</span></td><td><img src="../.gitbook/assets/image (10).png" alt="" data-size="original"></td><td>Dịch máy</td></tr></tbody></table>

### 1.3 Hàm Loss

Trong trường hợp của mạng Neral hồi quy, hàm mất mát L của tất cả các bước thời gian được định nghĩa dựa theo mất mát ở mọi thời điểm như sau:

$$
L(\hat{y},y)=\displaystyle{\sum_{t=1}^{T_y}L(\hat{y}^{<t>},y^{<t>})}
$$

### 1.4 Lan truyền ngược theo thời gian

Lan truyền ngược được hoàn thành ở mỗi một thời điểm cụ thể. Ở bước T, đạo hàm của hàm mất mát $$L$$ với ma trận trọng số W được biểu diễn như sau:

$$
\frac{\partial L^{(T)}}{\partial W}= \displaystyle{\sum_{t=1}^T}\frac{\partial L^{(T)}}{\partial W}
$$

## 2. Xử lí phụ thuộc dài hạn

### 2.1 Các hàm kích hoạt thường dùng

| Sigmoid                                                                   | Tanh                                                                      | ReLU                                                                      |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| $$g(z)=\frac{1}{1+e^{-z}}$$                                               | $$g(z)= \frac{e^z-e^{-z}}{e^z+e^{-z}}$$                                   | $$g(z)=max(0,z)$$                                                         |
| <img src="../.gitbook/assets/image (14).png" alt="" data-size="original"> | <img src="../.gitbook/assets/image (15).png" alt="" data-size="original"> | <img src="../.gitbook/assets/image (16).png" alt="" data-size="original"> |

### 2.2 Vanishing/exploding gradient

Hiện tượng vanishing và exploding gradient thường gặp trong ngữ cảnh của RNNs. Lí do tại sao chúng thường xảy ra đó là khó để có được sự phụ thuộc dài hạn vì multiplicative gradient có thể tăng/ giảm theo hàm mũ tương ứng với số lượng các tầng

### 2.3 Gradient clipping&#x20;

Là một kĩ thuật được sử dụng để giải quyết vấn đề exploding gradient xảy ra khi thực hiện lan truyền ngược. Bằng việc giới hạn giá trị lớn nhất cho gradient, hiện tượng này sẽ được kiểm soát trong thực tế

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

### 2.4 Các loại cổng

Để giải quyết vấn đề vanishing gradient, các cổng cụ thể được sử dụng trong một vài loại RNNs và thường có mục đích rõ ràng. Chúng thường được kí hiệu là $$\Gamma$$

$$
\Gamma =\sigma(Wx^{<t>}+Ua^{<t-1>}+b)
$$

Với W,U,b là các hệ số của một cổng và $$\sigma$$ là hàm sigmoid. Các loại chính được tổng kết ở bảng dưới đây

<table data-full-width="true"><thead><tr><th>Loại cổng </th><th>Vài trò</th><th>Được sử dụng trong</th></tr></thead><tbody><tr><td>Update Gate(cổng cập nhật) <span class="math">\Gamma u</span></td><td>Quyết định thông tin nào từ trạng thái cũ cần cập nhật dựa trên đầu vào mới.</td><td>GRU,LSTM</td></tr><tr><td>Reset Gate(Cổng reset)</td><td>Quyết định thông tin nào từ trạng thái cũ sẽ được sử dụng để tính toán trạng thái mới.</td><td>GRU</td></tr><tr><td>Input Gate(Cổng vào) <span class="math">\Gamma i</span></td><td>Quyết định thông tin nào từ đầu vào hiện tại sẽ được lưu trữ vào <strong>cell state</strong>.</td><td>LSTM, GRU(kết hợp với update gate)</td></tr><tr><td>Forget Gate(Cổng quên) <span class="math">\Gamma f</span></td><td>Quyết định thông tin nào từ trạng thái cũ (<strong>cell state</strong>) sẽ bị <strong>quên đi</strong>.</td><td>LSTM, GRU(kết hợp với update gate)</td></tr><tr><td>Output Gate(Cổng ra) <span class="math">\Gamma o</span></td><td>Quyết định thông tin nào từ <strong>cell state</strong> sẽ được đưa ra làm <strong>hidden state</strong> hiện tại.</td><td>LSTM</td></tr></tbody></table>

### 2.5 GRU/LSTM

Gated Recurrent Unit(GRU) và các đơn vị bộ nhớ dài- ngắn hạn (LSTM) dùng để đối phó với vấn đề gradient được gặp phải khi sử dụng mạng RNNs truyền thống, ta có LSTM là sự tổng quát của GRU.&#x20;



#### 2.5.1 LSTM ( Long short term memory)

<figure><img src="../.gitbook/assets/image (22).png" alt="Kiến trúc long short term memory"><figcaption><p><a href="https://www.mdpi.com/1424-8220/21/16/5625">https://www.mdpi.com/1424-8220/21/16/5625</a></p></figcaption></figure>

Tổng quan: LSTM là biến thể RNN mạnh mẽ hơn, được thiết kế đặc biệt để xử lý vấn đề vanishing gradient bằng cách thêm một **cell state** để lưu trữ thông tin lâu dài



<table data-full-width="true"><thead><tr><th width="100">Cấu trúc</th><th></th></tr></thead><tbody><tr><td>Trạng thái ô (cell state)</td><td>Dòng thông tin dài hạn, chỉ bị thay đổi bời các cổng</td></tr><tr><td>Trạng thái ẩn (hidden state)</td><td>Bộ nhớ ngắn hạn, được cập nhật mỗi bước thời gian</td></tr><tr><td>Cổng</td><td><ul><li>Forget gate</li><li>Input gate </li><li>Cell candidate gate</li><li>Outgate</li></ul><p><em>Thông thường cell candidate gate nằm trong input gate để quyết định số lượng kiến thức thực tế đã nhớ</em> </p></td></tr></tbody></table>



#### 2.5.2 GRU(Gated recurrent unit)

<figure><img src="../.gitbook/assets/image (23).png" alt="Kiến trúc GRU"><figcaption><p><a href="https://www.mdpi.com/1424-8220/21/16/5625">https://www.mdpi.com/1424-8220/21/16/5625</a></p></figcaption></figure>

**Tổng quan:** Đơn giản hóa LSTM, giảm chi phí tính toán. GRU sử dụng ít tham số hơn và loại bỏ cell state, thay vào đó nó sử dụng hidden state để lưu trữ thông tin.

<table data-full-width="true"><thead><tr><th width="100">Cấu trúc</th><th></th></tr></thead><tbody><tr><td>Không có trạng thái ô</td><td>Trạng thái ẩn đóng vai trò là cả bộ nhớ ngắn hạn và dài hạn</td></tr><tr><td>Cổng</td><td><ul><li>Reset gate</li><li>Update gate</li><li>Candidate state gate</li></ul><p><em>Thông thường cell candidate gate nằm trong Update gate để quyết định số lượng kiến thức thực tế đã nhớ</em></p></td></tr></tbody></table>

#### 2.5.3 So sánh LSTM và GRU

| Thuộc tính           | GRU                             | LSTM                         |
| -------------------- | ------------------------------- | ---------------------------- |
| Cổng                 | Update, Reset                   | Forget, Input, Output        |
| Số lượng tham số     | Ít hơn                          | Nhiều hơn                    |
| Cell State           | Không có                        | Có                           |
| Thời gian huấn luyện | Nhanh hơn                       | Chậm hơn                     |
| Xử lý chuỗi dài      | Kém hơn                         | Tốt hơn                      |
| Ứng dụng             | Dữ liệu ít phức tạp, chuỗi ngắn | Chuỗi dài, bài toán phức tạp |

### 2.6 Các biến thể của RNN

<table data-full-width="true"><thead><tr><th width="151"></th><th>RNN hai chiều (Bidirectional, BRNN)</th><th>RNN sâu(Deep, DRNN)</th></tr></thead><tbody><tr><td>Cấu trúc</td><td><img src="../.gitbook/assets/image (25).png" alt="" data-size="original"></td><td><img src="../.gitbook/assets/image (26).png" alt="" data-size="original"></td></tr><tr><td>Ưu điểm</td><td><p></p><ul><li><strong>Ngữ cảnh đầy đủ:</strong><br>Có thể sử dụng thông tin từ cả hai chiều của chuỗi.</li><li><p><strong>Hiệu quả trong các bài toán như:</strong></p><ul><li>Dịch máy (Machine Translation).</li><li>Nhận diện giọng nói (Speech Recognition).</li><li>Gán nhãn chuỗi (Sequence Labeling).</li></ul></li></ul></td><td><p></p><ul><li><strong>Khả năng học biểu diễn cấp cao:</strong><br>Lớp RNN đầu tiên học các đặc trưng cơ bản, trong khi các lớp cao hơn học các biểu diễn phức tạp hơn.</li><li><p><strong>Hiệu quả trong các bài toán phức tạp:</strong></p><ul><li>Phân loại cảm xúc (Sentiment Analysis).</li><li>Nhận diện hình ảnh/video dựa trên chuỗi (Video Recognition).</li></ul></li></ul></td></tr><tr><td>Nhược điểm</td><td><ul><li><strong>Độ trễ cao:</strong><br>Vì cần toàn bộ chuỗi đầu vào để thực hiện backward pass, BRNN không phù hợp với các bài toán thời gian thực.</li><li><strong>Tốn tài nguyên:</strong><br>Gấp đôi số lượng tham số so với RNN tiêu chuẩn.</li></ul></td><td><p></p><ul><li><strong>Vanishing Gradient Problem:</strong> DRNN dễ gặp vấn đề gradient biến mất, đặc biệt khi không sử dụng LSTM hoặc GRU.</li><li><strong>Tốn tài nguyên:</strong> Cần nhiều thời gian và bộ nhớ để huấn luyện các lớp sâu.</li></ul><p></p></td></tr><tr><td>Ứng dụng</td><td>Nhận diện giọng nói, dịch máy</td><td>Phân tích chuỗi phức tạp</td></tr></tbody></table>

#### Kết hợp BRNN và DRNN&#x20;

Một số hệ thống hiện đại sử dụng Deep BRNN, tức là xếp chồng nhiều lớp BRNN để tận dụng cả hai lợi thế độ sâu của DRNN và ngữ cảnh đầy đủ của BRNN



