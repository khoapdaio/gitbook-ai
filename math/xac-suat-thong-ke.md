---
icon: chart-scatter-bubble
---

# Xác suất thống kê

## 1. Counting&#x20;

### 1.1 Quy tắc nhân

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png" alt="" width="540"><figcaption></figcaption></figure>

Giả sử chúng ta có một thí nghiệm hợp chất (một thí nghiệm có nhiều thành phần). Nếu thành phần thứ nhất có n1 kết quả có thể xảy ra, thành phần thứ hai có n2 kết quả có thể xảy ra, . . . và thành phần thứ r có nr kết quả có thể xảy ra, thì tổng thể có n1n2 . . . nr khả năng cho toàn bộ thí nghiệm

### 1.2 Bảng lấy mẫu

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Bảng lấy mẫu cung cấp số lượng mẫu có thể có kích thước k trong một quần thể có kích thước n, theo nhiều giả định khác nhau về cách thu thập mẫu.

|                     | Order  Matter         | Not Matter                                  |
| ------------------- | --------------------- | ------------------------------------------- |
| With Replacement    | $$n^k$$               | $$\begin{pmatrix}n+k-1 \cr k\end{pmatrix}$$ |
| Without Replacement | $$\frac{n!}{(n-k)!}$$ | $$(\frac{n}{k})$$                           |

### 1.3 Định nghĩa xác suất về Naive

Nếu tất cả kết quả có khả năng xảy ra như nhau thì xác suất xảy ra sự kiện A là:

$$
P_{naive}(A)=\frac{\text{Số lượng kết quả thuận lợi cho A}}{\text{Số lượng kết quả}}
$$

## 2. Suy nghĩ có điều kiện

### 2.1 Sự cô lập

Biến cố độc lập A và B là độc lập nếu biết A có xảy ra hay không thì không cung cấp thông tin về việc B có xảy ra hay không. Chính thức hơn, A và B (có xác suất khác không) là độc lập nếu và chỉ nếu một trong các tuyên bố tương đương sau đây là đúng:

$$
P(A\cap B)= P(A)P(B)
$$

$$
P(A|B) =P(A)
$$

$$
P(B|A) = P(B)
$$

Độc lập có điều kiện A và B là độc lập có điều kiện với C nếu P (A ∩ B|C) = P (A|C)P (B|C). Độc lập có điều kiện không ngụ ý độc lập, và độc lập không ngụ ý độc lập có điều kiện

### 2.2 Hợp, Giao và Bổ sung

Định luật De Morgan:;  A Một điều kiện hưu ích có thể giúp tính toán xác xuất của phép Hợp bằng  cách liên hệ chúng với phép Giao hoán và ngược lại. Kết quả tương tự đúng với nhiều hơn hai tập hợp.

$$
(A\cup B)^c= A^c\cap B^c
$$

$$
(A\cap B)^c= A^c\cup B^c
$$

### 2.3 Khớp, cận biên và có điều kiện

Xác suất khớp $$P(A\cap B) \text{ hoặc }P(A,B)$$ - Xác suất của A và B

Xác suất (Không điều kiện) cận biên $$P(A)$$ -  Xác suất của A

Xác suất có điều kiện $$P(A|B)= P(A,B)|P(B)$$ -  Xác suất của A,  với điều kiện B đã xảy ra

Xác suất có điều kiện là xác suất  $$P(A|B)$$ là hàm xác suât cho bất kỳ B cố định nào. Bất kỳ định lý nào đúng với xác suất cũng đúng với xác suất có điều kiện.



### 2.4 Xác suất của một giao điểm hoặc hợp nhất

Giao điểm thông qua điều kiện

$$
P(A,B) =P(A)P(B|A)
$$

$$
P(A,B,C)= P(A)P(B|A)P(C|A,B)
$$

Công đoàn thông qua Bao gồm - Loại trừ

$$
P(A\cup B) = P(A)+ P(B) - P(A\cap B)
$$

$$
P(A\cup B\cup C)= P(A)+P(B)+P(C)-P(A\cap B)-P(A\cap C)-P(B\cap C)+P(A\cap B\cap C)
$$

### 2.5 Nghịch lý Simpson

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Có thể có:

$$
P(A|B,C)<P(A|B^c,C) \text{ và } P(A|B,C^c)<P(A|B^c,C^c)
$$

Nhưng cũng có thể:

$$
P(A|B)>P(A|B^c)
$$

### 2.6 Quy luật xác suất toàn phần (LOTP)

Cho B1, B2, B3, ...Bn là một phân hoạch của không gian mẫu (tức là chúng rời nhau và hợp của chúng là toàn bộ không gian mẫu).

$$
P(A)= P(A|B_1)P(B_1)+P(A|B_2)P(B_2)+...+P(A|B_n)P(B_n)
$$

$$
P(A)= P(A\cap B_1)+P(A\cap B_2)+...+ P(A\cap B_n)
$$

Với LOTP có điều kiện bổ sung, chỉ cần thêm một sự kiện C nữa:

$$
P(A|C)= P(A|B_1,C)P(B_1|C)+...+P(A|B_n,C)P(B_n|C)
$$

$$
P(A|C)= P(A\cap B_1|C)+P(A\cap B_1|C)+P(A\cap B_2|C) +...+ P(A\cap B_n|C)
$$

Trường hợp đặc biệt của LOTP với $$B\text{ và }B^c$$ là phân vùng:

$$
P(A)=P(A|B)P(B)+P(A|B^c)P(B^c)
$$

$$
P(A)=P(A\cap B)+P(A\cap B^c)
$$

### 2.7 Quy tắc Bayes'&#x20;

Quy tắc Bayes và với điều kiện bổ sung (Chỉ cần thêm C!)

$$
P(A|B)=\frac{P(B|A)P(A)}{P(B)}
$$

$$
P(A|B,C)=\frac{P(B|A,C)P(A|C)}{P(B|C)}
$$

Chúng ta cũng có thể viết như sau:

$$
P(A|B,C)=\frac{P(A,B,C)}{P(B,C)}=\frac{P(B,C|A)P(A)}{P(B,C)}
$$

Dạng Odds(Tỷ lệ cược) của quy luật Bayes':

$$
\frac{P(A|B)}{P(A^c|B)}=\frac{P(B|A)}{P(B|A^c)}\frac{P(A)}{P(A^c)}
$$

Tỷ lệ cược của A là tỷ lệ khả năng nhân(Likelihood ratio) với tỉ lệ cược trước đó(Prior odds)



## 3 Biến ngẫu nhiên và phân phối của chúng

### **PMF, CDF và Hàm khối lượng**&#x20;

\
Xác suất độc lập PMF cung cấp xác suất một biến ngẫu nhiên rời rạc nhận giá trị x

$$
\text{px}(x) =P(X=x)
$$

<figure><img src="../.gitbook/assets/image (4) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

PMF thỏa mãn

$$
\text{px}(x)\ge 0 \text{ và }\displaystyle{\sum}\text{px}(x)=1
$$

Hàm phân phối tích lũy (CDF) cung cấp xác suất một biến ngẫu nhiên nhỏ hơn hoặc bảng x

$$
F_X(x)=P(X \le x)
$$

<figure><img src="../.gitbook/assets/image (6) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<div data-full-width="false"><figure><img src="../.gitbook/assets/image (5) (1) (1) (1).png" alt=""><figcaption></figcaption></figure></div>

CDF là một hàm tăng liên tục bên phải với:

$$
F_X(x)\to 0 \text{ as }x\to -\infin \text{ and } F_X(x)\to 1 \text{ as }x\to \infin
$$

Độc lập theo trực giác, hai biến ngẫu nhiên được coi là độc lập nếu biết giá trị của biến này không cung cấp thông tin và biến kia&#x20;

Các r.v.s X và Y  là độc lập nếu với mọi giá trị của x và y

$$
P(X=x, Y=y)=P(X=x)P(Y=y)
$$

## 4. Giá trị kỳ vọng và các chỉ số

### 4.1 Giá trị kỳ vọng và tính tuyến tính

Giá trị kỳ vọng (hay còn gọi là trung bình, kỳ vọng hoặc giá trị trung bình cộng) là giá trị trung bình có trọng số của các kết quả có thể xảy ra của biến ngẫu nhiên.

Về mặt toán học nếu x1, x2, x3, ... là tất cả các giá trị riêng biệt có thể mà X có thể nhận được, thì giá trị mong đợi của X là:

$$
E(X)=\displaystyle{\sum_i}x_i P(X=x_i)
$$

|  X  |  Y  | X+Y |
| :-: | :-: | :-: |
|  3  |  4  |  7  |
|  2  |  2  |  4  |
|  6  |  8  |  14 |
|  10 |  23 |  33 |
|  1  |  -3 |  -2 |
|  1  |  0  |  1  |
|  5  |  9  |  14 |
|  4  |  1  |  5  |
| ... | ... | ... |

$$
\frac{1}{n}\displaystyle{\sum_{i=1}^n}x_i\quad\quad\quad\quad\quad+\quad\quad\quad\quad\quad\quad\frac{1}{n}\displaystyle{\sum_{i=1}^n}\quad\quad\quad\quad\quad=\quad\quad\quad\quad\frac{1}{n}\displaystyle{\sum_{i=1^n}}(x_i+y_i)
$$

$$
E(X)\quad\quad\quad\quad\quad+\quad\quad\quad\quad\quad\quad E(Y)\quad\quad\quad\quad\quad=\quad\quad\quad\quad E(X+Y)
$$

Tính tuyến tính đối với mọi r.v.s X và Y, và các hàng số a,b,c

$$
E(aX+bY+c)=aE(X)+bE(Y)+c
$$

Phân phối giống nhau ngụ ý cùng một giá trị trung bình nếu X và Y có cùng phân phối , thì E(X)=E(Y) và nói chung hơn

$$
E(g(X))=E(g(Y))
$$

Giá trị kỳ vọng có điều kiện được định nghĩa giống như kỳ vọng, chỉ khác là có điều kiện dựa trên bất kỳ sự kiên A nào

$$
E(X|A)=\displaystyle{\sum_x}P(X=x|A)
$$

### 4.2 Chỉ báo biến ngẫu nhiên&#x20;

Chỉ báo biến ngẫu nhiên là một biến ngẫu nhiên có giá tị là 1 hoặc 0. Nó luôn là chỉ báo của mố số sự kiện: nếu sự kiện xảy ra, chỉ báo là 1: nếu không, chỉ báo là 0. Chúng hữu ích cho nhiều bài toán về việc đến số lượng sự kiên nào đó xảy ra. Viết&#x20;

$$
I_A=\begin{cases}
1 \text{ nếu A xảy ra}\cr
0 \text{ nếu A không xảy ra }
\end{cases}
$$

Lưu ý rằng $$I^2_A=I_A,I_AI_B=I_{A\cap B},\text{ và } I_{A\cup B} =I_A+I_B-I_AI_B$$

Phân phối $$I_A \sim Bern(P)\text{ khi }p=P(A)$$

### 4.3 Phương sai và độ lệch chuẩn

$$
Var(X)=E(X-E(X))^2=E(X^2)-(E(X))^2
$$

$$
SD(X)=\sqrt{Var(X)}
$$

## 5. RV liên tục, LOTUS, UoU

### 5.1 Biến ngẫu nhiên liên tục (CRV)

Xác suất CRV nằm trong một khoảng là bao nhiêu? Lấy sự khác biệt trong các giá trị CDF (hoặc sử dụng PDF như mô tả sau)

$$
P(a\le X\le b)= P(X\le b)-P(X\le a)=FX(b)-FX(a)
$$

Với $$X \sim N(\mu,\sigma^2)$$, điều đó trở thành

$$
P(a\le X\le b)=\Phi \begin{bmatrix}\frac{b-\mu}{\sigma}\end{bmatrix}-\Phi\begin{bmatrix}\frac{a-\mu}{\sigma}\end{bmatrix}
$$

Hàm mật độ xác suất (PDF) là gì ? PDF f là đạo hàm của CDF F

$$
F'(x) =f(x)
$$

PDF không âm và tích phân thành 1. Theo định lý cơ bản của phép tính, để chuyển từ PDF trở lại CDF, chúng ta có thể tích phân:

$$
F(x)=\displaystyle{\int_{-\infin}^x f(t)dt}
$$

<figure><img src="../.gitbook/assets/image (9) (1) (1).png" alt=""><figcaption></figcaption></figure>

Để tìm xác suất CRV nhận giá trị trong một khoảng, hãy tích phân PDF trên khoảng đó

$$
F(b)-F(a)=\displaystyle{\int_a^b} f(x)dx
$$

Làm thế nào để tìm giá trị kỳ vọng của CRV? Tương tự như trường hợp rời rạc, khi bạn cộng x lần PMF, đói với CRV, bạn tích phân x lần PDF

$$
E(X)=\displaystyle{\int_{-\infin}^{\infin}}xf(x)dx
$$

### 5.2  LOTUS

Giá trị kỳ vọng của một hàm số RV Giá trị kỳ vọng của X được định nghĩa theo cách này:

$$
E(X)= \displaystyle{\sum_x}xP(X=x)(\text{Đối với X rời rạc})
$$

$$
E(X)= \displaystyle{\int_{-\infin}^{\infin}} xf(x)dx(\text{Đối với X liên tục})
$$

**Hàm của biến ngẫu nhiên là gì?** Hàm của một biến ngẫu nhiên cũng là biến ngẫu nhiên. Ví dụ, nếu X là số xe đạp bạn nhìn thấy trong một giờ, thì g(x) = 2X là bánh xe đạp bạn nhìn thấy trong giờ đó và $$h(X)=\begin{bmatrix} x \cr 2 \end{bmatrix} = \frac{X(X-1)}{2}$$  là số cặp xe đạp sao cho bạn nhìn thấy cả hai chiếc xe đạp đó trong giờ đó&#x20;



Ý nghĩa là gì? Bạn không cần biết PMF/PDF của g(x) để tìm giá trị kỳ vọng của nó. Tất cả những gì bạn cần là PMF/PDF của X



### 5.3 Tính phổ quát đồng nhất&#x20;

Khi bạn cắm bất kỳ CRV nào vào CDF của chính nó, bạn sẽ nhận được một biến ngẫu nhiên Uniform(0,1). Khi bạn cắm một rv Uniform (0,1) vào một CDF nghịch đảo, bạn sẽ nhận được một rv với CDF đó. Ví dụ, giả sử một biến ngẫu nhiên X có CDF

$$
F(x)= 1-e^{-x}, \text{ với }x>0
$$

Theo UoU, nếu chúng ta đựa X vào hàm này thì chúng ta sẽ có được một biến ngẫu nhiên phân phối đều.

$$
F(X)=1-e^{-X} \sim Unif(0,1)
$$

Tương tự như vậy , nếu $$U \sim Unif(0,1)$$ thì $$F^{-1} (U)$$ có CDF F. Điểm mấu chốt là F đối với bất kỳ biến ngẫu nhiên liên tục X nào, chúng ta có thể biến đổi nó thành biến ngẫu nhiên đồng nhất và ngược lại bằng các sử dụng CDF của nó.



## 6. Moment và MGF

### 6.1 Moment

Các mô men mô tả hình dạng của một phân phối. Giả sử X có giá trị trung bình $$\mu$$ và độ lệch chuẩn $$\sigma$$, và   $$Z = (X-\mu)/\sigma$$ là phiên bản chuẩn hóa của X. Mô men thứ k của X là $$\mu k=E(X^k)$$ và mô men chuẩn hóa thứ k của X là $$m_k=E(Z^k)$$. Giá trị trung bình, phương sai, độ lệch và Kurtosis là những bản tóm tắt quan trọng về hình dạng của một bản phân phối&#x20;

Mean $$E(X) =\mu_1$$

Variance $$Var(X) = \mu_2 - \mu_1^2$$

Skewness $$Skew(X) =m_3$$

Kurtosis $$Kurt(X) =m_4 -3$$

### 6.2 Hàm tạo Moment

MGF Cho tất cả các biến ngẫu nhiên X, hàm:

$$
M_X(t)=E(e^{tX})
$$

là hàm tạo mô men (MGF) của X, nếu nó tồn tại với mọi t trong một khoảng mở nào đó chứa 0. Biến t cũng có thể được gọi là u hoặc v. Đây là một thiết bị ghi sổ cho phép chúng ta làm việc với hàm MX thay vì chuỗi các mô men



**Tại sao nó được gọi là Hàm tạo mô men?** Bởi vì đạo hàm bậc k của hàm tạo mô men, được đánh giá tại 0, là mô men bậc k của X.

$$
\mu_k= E(X^k)=M_X^{(k)}(0)
$$

Điều này đúng theo sự khai triển của Taylor của $$e^{tX}$$, thì

$$
M_X(t) =E(e^{tX})=\displaystyle{\sum_{k=0}^{\infin}}\frac{E(X^k)t^k}{k!}=\displaystyle{\sum_{k=0}^{\infin}}\frac{\mu_kt^k}{k!}
$$

MGF của các hàm tuyến tính nếu chúng ta có $$y=aX+b$$, thì

$$
M_Y(t)=E(e^{t(aX+b)})= e^{bt}E(e^{atX})=e^{bt}Mx(at)
$$

Tính duy nhất  Nếu nó tồn tại, MGF xác định phân phối duy nhất. Điều này có nghĩa là đối với bất kỳ hai biến ngẫu nhiên X và Y nào, chúng được phân phối giống nhau (PMF/PDF của chúng bằng nhau) nếu và chỉ nếu MGF của chúng bằng nhau.

Tổng hợp các RV đọc lập bằng cách nhân các MGF. Nếu X và Y độc lập, thì

$$
M_{X+Y}(t)=E(e^{t(X+Y)})=E(e^{tX})E(e^{tY})= M_X(t).M_Y(t)
$$

MGF của tổng hai biến ngẫu nhiên là tích các MGF của hai biến ngẫu nhiên đó
