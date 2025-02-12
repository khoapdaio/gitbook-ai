# Transformers

## 1. Overview

Transformer là một mô hình deep learning được giới thiệu trong bài báo nổi tiếng "Attention Is All You Need" (2017). Nó thay thế các mô hình tuần tự như RNN và LSTM bằng cách sử dụng cơ chế attention cho phép xử lý song song. Nó được sử dụng chủ yếu ở linh vực xử lý ngôn ngữ tự nhiên (NLP) và thị giác máy tính (CV)

Trích dẫn từ bài báo

> Transformer là mô hình chuyển đổi đầu tiên hoàn toàn dựa vào sự tự chú ý để tính toán biểu diễn đầu vào và đầu ra không sử dụng RNN được căn chỉnh theo trình tự hoặc phép tích chập

## 2. Kiến trúc của Tranformer



<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>(Nguồn: https://arxiv.org/abs/1706.03762)</p></figcaption></figure>

Kiến trúc Transformer gồm 2 thành phần chính:

* Encoder: Chịu trách nhiệm chuyển đổi đầu vào thành biểu diễn trung gian
* Decoder: Sử dụng biểu diễn đó để tạo đầu ra&#x20;

Cả hai đều bao gồm các lớp như:&#x20;

* Multi-Head Attention
* Feedforward Neural Networks
* Residual Connection
* Positional Encoding&#x20;

Tiếp theo sẽ&#x20;

## 3. Attention Mechanism

### 3.1  Overview

Attention Mechanism ra đời từ nhu cầu giảm sự phụ thuộc tuần tự và tập trung vào các thông tin quan trọng, giúp các mô hình AI xử lý dữ liệu hiệu quả hơn, đặc biệt với chuỗi dài và phức tạp.

Cơ chế chú ý bao gồm 3 thành phần chính, là **Query**, **Key**, và**Value**

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>Nguồn <a href="https://steveimm.id/posts/transformer-cheatsheet/#scaled-dot-product-attention">https://steveimm.id/posts/transformer-cheatsheet/#scaled-dot-product-attention</a></p></figcaption></figure>

Ý tưởng chính của Attention Machanism:

* Chọn lọc thông tin: Thay vì dựa hoàn toàn vào context vector, Attention Mechanism cho phép mô hình tập trung vào các phần quan trọng nhất của đầu vào liên quan đến đầu ra hiện tại
* Tăng khả năng học phụ thuộc dài hạn: Attention giúp mô hình trục tiếp kết nối với các token ở các vị trí xa nhau mà không cần thông qua trạng thái tuần tự
* Làm giảm mất mát thông tin: Mỗi đầu ra được tính bằng cách tham chiếu đến toàn bộ đầu vào, thay vì chỉ phụ thuộc vào một vector nén

### 3.2 Scaled Dot-Product Attention

Tính tích vô hướng giữa Q và K, sau đó chuẩn hóa và nhân với V.&#x20;

Công thức Attention:



$$
Attention(Q,K,V)=softmax(\frac{QK^T}{\sqrt{d_k}})V
$$



* Q (Query): Đại diện cho vector tìm kiếm thông tin.
* K (Key): Đại diện cho vector chứa thông tin.
* V (Value): Đại diện cho thông tin cần truy xuất.
* $$d_k$$​: Kích thước của vector Key.

<div data-full-width="true"><figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption><p>Nguồn <a href="https://steveimm.id/posts/transformer-cheatsheet/#scaled-dot-product-attention">https://steveimm.id/posts/transformer-cheatsheet/#scaled-dot-product-attention</a></p></figcaption></figure></div>

* $$QK^T$$ là phép nhân ma trận, tính điểm tương quan giữa các truy vấn $$Q$$ và các khóa $$K$$. Mỗi phân tử trong kết quả biểu diễn mức độ liên quan (similarity) giữa một phần tử trong truy vấn với tất cả các phần tử trong khóa. Vì đay là dot product(tích vô hướng), một cách hiệu quả để đo độ tương đồng giữa các vector
* $$\sqrt{d_k}$$ là các căn bậc hai của số chiều của vector khóa $$d_k$$. Chia cho $$\sqrt{d_k}$$ giúp ổn định giá trị, giữ các điểm tương quan trong phạm vi hợp lý
* Softmax chuyển đổi các điểm tương quan thành xác suất
* Nhân với V ta được kết quả cuối cùng là ma trận chứa thông tin đã được tập trung từ các phần tử quan trọng nhất

### 3.3 Multi-Head Attention

Sử dụng nhiều "Head" để học các mối quan hệ khác nhau trong dữ liệu. Mỗi Head là một phép tính Attention riêng biệt

Công thức:

$$
MHA(Q,K,V)=Concat(head1,head2,...,head_h)W^o
$$

Trong đó

$$
head_i=Attention(QW^Q_i,KW_i^K,VW^V_i)
$$



<div data-full-width="true"><figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption><p>Nguồn <a href="https://steveimm.id/posts/transformer-cheatsheet/#scaled-dot-product-attention">https://steveimm.id/posts/transformer-cheatsheet/#scaled-dot-product-attention</a></p></figcaption></figure></div>



### 3.4 Self-Attention

Tự học mối quan hệ giữa các từ trong cùng một câu hoặc chuỗi.

### 3.5 Cross-Attention

Liên kết giữa hai chuỗi khác nhau, như trong Decoder của Transformer(liên kết đầu vào và đầu ra )



## 4. Positional Encoding

Positional Encoding(PE) cung cấp thông tin về thứ tự của các từ trong chuỗi dựa trên việc gán gái trị số cho mỗi vị trí để mô hình hiểu được mối quan hệ tuấn tự trong chuỗi. Do đó Transformer không có cơ chế tuần tự như RNN

Công thức:

$$
PE(pos,2i)=\sin(\frac{pos}{10000^{\frac{2i}{d_{model}}}})
$$

$$
PE(pos,2i+1)=\cos(\frac{pos}{10000^{\frac{2i}{d_{model}}}})
$$

* **pos:** Vị trí trong chuỗi (position).
* **i:** Chỉ số chiều (dimension index).
* $$d_{\text{model}}$$: Số chiều của vector nhúng (embedding dimension).

<div data-full-width="true"><figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption><p>Nguồn <a href="https://machinelearningmastery.com/">https://machinelearningmastery.com/</a></p></figcaption></figure></div>

## 5.Positionwise Feed-Forward Neural Network (Feed Forward Network - FFN)

### 5.1 Motivation

**Vấn đề**: Mặc dù các cơ chế tự chú ý (self-attention) giúp transformer nắm bắt được mối quan hệ dài hạn trong chuỗi dữ liệu, chúng không dủ mạnh để mô hình hóa các tương tác phi tuyến giữa các đặc trưng cho từng vị trí (token) riêng lẻ



⇒ Một mạng neural network lan truyền tiến vị trí  FFN được sử dụng sau cơ chế tự chú ý để thực hiện học các biểu diễn phi tuyến cho từng vị trí một cách độc lập

### 5.2 Kiến trúc

FFN áp dụng một mạng nơ-ron hai lớp cho từng token trong chuỗi&#x20;

**Công thức:**

$$
FFN(x)= ReLU(xW_1+b_1)W_2+b_2
$$

* W1​,W2​: Ma trận trọng số (weights) của các lớp.
* $$\mathbf{b}_1, \mathbf{b}_2$$​: Hệ số bias tương ứng.
* ReLU: Hàm kích hoạt phi tuyến.

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption><p>nguồn <a href="https://zenn.dev/attentionplease/articles/1a01887b783494">https://zenn.dev/attentionplease/articles/1a01887b783494</a></p></figcaption></figure>

### 5.3 Ưu/ nhược điểm

| Ưu điểm                                                                                                                                                                                                                                                                                                                                                                                     | Nhược điểm                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <ul><li><strong>Độc lập vị trí:</strong> Xử lý từng vị trí riêng lẻ, giúp mô hình hóa đặc điểm cục bộ của mỗi token.</li><li><strong>Đơn giản và hiệu quả:</strong> Kiến trúc dễ triển khai, tận dụng khả năng song song hóa cao trên GPU/TPU.</li><li><strong>Kết hợp tốt với self-attention:</strong> Tăng cường biểu diễn cục bộ và toàn cục khi kết hợp cùng cơ chế tự chú ý.</li></ul> | <ul><li><strong>Không tận dụng thông tin vị trí:</strong> Vì xử lý độc lập từng token, FFN không nắm bắt được mối liên kết giữa các vị trí. Điều này được bù đắp bởi cơ chế tự chú ý.</li><li><strong>Phụ thuộc vào hyperparameters:</strong> Hiệu quả của FFN phụ thuộc vào các siêu tham số như kích thước ẩn của tầng trung gian ( <span class="math">d_{\text{ff}}</span>​).</li></ul> |





## 6. Cách hoạt động

### Bước 1: Preprocessing(tiền xử lý)

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption><p>nguồn <a href="https://200lab.io/blog/transformer-cong-nghe-dang-sau-chatgpt-va-bard/">https://200lab.io/blog/transformer-cong-nghe-dang-sau-chatgpt-va-bard/</a></p></figcaption></figure>

1. **Tokenization**: Dữ liệu đầu vào được biến đổi thành token. Ví dụ, câu "AI agent sẽ phát triển" sẽ được mã hoá thành 4 token \["AI, "agent", "sẽ", "phát", "triển"].
2. **Embedding**: Biến token thành vector. Mỗi token được chuyển thành một vector.
3. **Positional Encoding**: Vì Transformer không xử lý tuần tự nên cần một cách để hiểu vị trí của từng từ trong câu. Điều này được thực hiện thông qua positional encodings, được cộng trực tiếp vào input embeddings. Các positional encodings có thể dùng các hàm sin và cos với bước sóng khác nhau để mỗi vị trí có một encoding duy nhất.

### Bước 2: Encoder

Encoder bao gồm nhiều layer (lớp) xếp chồng lên nhau (stack). Mỗi layer có 2 sublayer là **Multi-Head Attention** và **Feed Forward Network (FNN)**. Output của 2 sublayer sẽ đi qua một lớp gọi là **Add & Norm.**

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

* [**Multi-head Attention**](transformers.md#id-3.3-multi-head-attention): Cho phép mô hình xử lý đồng thời các không gian con (subspaces) khác nhau bằng cách sử dụng nhiều "heads". Mỗi head tập trung vào các phần khác nhau của đầu vào, giúp nắm bắt thông tin đa dạng hơn.
* [**Positionwise Feed-forward Neural Network (FNN)**](transformers.md#id-5.positionwise-feed-forward-neural-network-feed-forward-network-ffn): Vector đầu ra từ các attention heads được truyền qua mạng FNN riêng cho từng head. Điều này tạo biểu diễn phi tuyến tính, giúp mô hình học các mối quan hệ phức tạp trong dữ liệu.
* **Add & Norm**: Residual connection (Add) giảm mất độ dốc trong mạng sâu, và layer normalization (Norm) ổn định quá trình huấn luyện, tăng hiệu quả học.

### Bước 3: Decoder

Tương tự Encoder, Decoder cũng có 2 sublayer và có thêm 1 sublayer ở nằm giữa 2 sublayer tên là **Encode-decode Attention**.

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

* **Masked Multi-Head Attention**: Là một biến thể của Multi-Head Attention, hoạt động tương tự Multi-Head Attention nhưng có "mask" để đảm bảo rằng các vị trí trong output chỉ có thể tập trung vào các từ trước đó mà không "nhìn thấy" các từ tiếp theo (điều này quan trọng cho quá trình dự đoán từ tiếp theo).
* **Multi-Head Attention**: Hoạt động giống với bước Encoder.
* **Encode-decode Attention**: Trong Encode-decode Attention, truy vấn tới từ đầu ra của lớp con Attention, còn key và value tới từ đầu ra của Encoder.
* **Positionwise Feed-forward Neural Network (FNN)**: Hoạt động giống với bước Encoder.
* **Add & Norm**: Hoạt động giống với bước Encoder.

**Đầu ra của Decoder**: Là chuỗi các vector, mỗi vector đại diện cho một từ trong chuỗi đầu ra. Các vector được đưa qua lớp tuyến tính và hàm softmax để tạo phân phối xác suất trên từ điển. Từ có xác suất cao nhất được chọn làm từ dự đoán tiếp theo, quy trình lặp lại đến khi gặp ký tự kết thúc câu hoặc đạt độ dài tối đa.





