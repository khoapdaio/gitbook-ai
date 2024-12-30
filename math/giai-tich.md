# 🔎 Giải tích

## 1. Giới hạn

### 1.1 Định nghĩa

**Precise Definition (Định nghĩa chính xác)**:&#x20;

Chúng ta nói $$\displaystyle{\lim_{x \to a}}f(x) = L$$ nếu với mỗi $$\epsilon >0$$ có $$\delta >0$$ sao cho bất cứ khi nào  $$0<|x-a|<\delta$$ thì$$|f(x) - L|<\epsilon$$



**“Working” Definition (Định nghĩa hoạt động)**:&#x20;

Chúng ta nói $$\displaystyle{\lim_{x \to a}}f(x) = L$$ nếu chúng ta có thể khiên $$f(x)$$ gần với L như chúng ta muốn bằng việc lấy $$x$$ đủ gần với $$a$$ (ở hai bên của $$a$$) mà không để $$x=a$$



**Right hand limit:**&#x20;

$$\displaystyle{\lim_{x \to a^+}}f(x) = L$$. Công thức này có định nghĩa giống limit ngoại trừ việc nó yêu cầu $$x>a$$



**Left hand limit:**

$$\displaystyle{\lim_{x \to a^-}}f(x) = L$$. Công thức này có định nghĩa giống limit ngoại trừ việc nó yêu cầu $$x<a$$



**Limit at Infinity:**

Chúng ta nói $$\displaystyle{\lim_{x \to \infin}}f(x) = L$$ nếu có thể khiến $$f(x)$$ gần với L mà chúng ta muốn bằng cách lấy giá trị của x đủ lớn và dương

Có một định nghĩa tương tự cho $$\displaystyle{\lim_{x \to -\infin}}f(x) = L$$ ngoại trừ việc chúng ta cần x lớn và âm



**Infinite Limit:**&#x20;

Chúng ta nói $$\displaystyle{\lim_{x \to a}}f(x) = \infin$$ nếu chúng ta có thể khiến f(x) lớn tùy ý (và dương ) bằng cách lấy x đủ gần với a (hai phía của a) mà không để x = a



Có một định nghĩa tương tự cho $$\displaystyle{\lim_{x \to a}}f(x) = -\infin$$  trừ việc chúng ta làm cho $$f(x)$$ lớn tùy ý và âm

### 1.2 Mối quan hệ giữa giới hạn và giới hạn một phía

$$\displaystyle{\lim_{x \to a}}f(x) = L \Rightarrow \displaystyle{\lim_{x \to a^+}}f(x) = \displaystyle{\lim_{x \to a^-}}f(x) = L$$

Ngược lại

$$\displaystyle{\lim_{x \to a^+}}f(x) = \displaystyle{\lim_{x \to a^-}}f(x) = L\Rightarrow \displaystyle{\lim_{x \to a}}f(x) = L$$

Còn&#x20;

$$\displaystyle{\lim_{x \to a^+}}f(x) \ne \displaystyle{\lim_{x \to a^-}}f(x)  \Rightarrow \displaystyle{\lim_{x \to a} f(x)}$$ Không tồn tại



### 1.3 Tính chất

Giả sử $$\displaystyle{\lim_{x \rightarrow a }f(x)}$$ và $$\displaystyle{\lim_{x \rightarrow a }g(x)}$$ cả hai đều tồn tại và c là bất kỳ số nào sau đó

1. $$\displaystyle{\lim_{x \to a}}[c.f(x)] =c. \displaystyle{\lim_{x \to a}}f(x)$$
2. $$\displaystyle{\lim_{x \to a}}[f(x) \pm g(x)] = \displaystyle{\lim_{x \to a}}f(x)\pm \displaystyle{\lim_{x \to a}}g(x)$$
3. $$\displaystyle{\lim_{x \to a}}[f(x).g(x)] = \displaystyle{\lim_{x \to a}}f(x). \displaystyle{\lim_{x \to a}}g(x)$$
4. $$\displaystyle{\lim_{x \to a}}[\frac{f(x) }{ g(x)}] = \frac{\displaystyle{\lim_{x \to a}}f(x)}{\displaystyle{\lim_{x \to a}}g(x) }$$
5. $$\displaystyle{\lim_{x \to a}}[f(x)^n] = [\displaystyle{\lim_{x \to a}}f(x)]^n$$
6.  $$\displaystyle{\lim_{x \to a}}[\sqrt[2]{f(x)}] = \sqrt[2]{\displaystyle{\lim_{x \to a}}f(x)}$$



### 1.4 Đánh giá giới hạn cơ bản tại $$\pm \infin$$

Note: sgn(a) = 1 nếu a > 0 và sgn(a) = -1 nếu a<0.

1. $$\displaystyle{\lim_{x \to \infin}e^x }= \infin$$ & $$\displaystyle{\lim_{x \to -\infin}e^x }= 0$$
2. $$\displaystyle{\lim_{x \to \infin}ln(x) }= \infin$$ & $$\displaystyle{\lim_{x \to +\infin}ln(x) }= -\infin$$
3. Nếu r > 0 thì $$\displaystyle{\lim_{x \to \infin}\frac{b}{x^{\gamma}} }= 0$$
4. Nếu r > 0 và $$x^{\gamma}$$ là số thực với x âm thì $$\displaystyle{\lim_{x \to \infin}\frac{b}{x^{\gamma}} }= 0$$
5. n chẵn: $$\displaystyle{\lim_{x \to \pm \infin}x^n }= \infin$$
6. n lẻ: $$\displaystyle{\lim_{x \to \infin}x^n }= \infin$$ & $$\displaystyle{\lim_{x \to -\infin}x^n }= -\infin$$
7. n chẵn: $$\displaystyle{\lim_{x \to \pm \infin}ax^n + .. + bx+c}= sgn(a)\infin$$
8. n lẻ: $$\displaystyle{\lim_{x \to \infin}ax^n + .. + bx+c}= sgn(a)\infin$$
9. n lẻ: $$\displaystyle{\lim_{x \to - \infin}ax^n + .. + bx+c}= -sgn(a)\infin$$

### 1.5 Các kỹ thuật đánh giá

1. Continuous Function\
   Nếu $$f(x)$$ là liên tục tại $$a$$ thì $$\displaystyle{\lim_{x \to a}f(x)} = f(a)$$\

2. Continuous Functions and Composition\
   $$f(x)$$ là liên tục tại b và $$\displaystyle{\lim_{x \to a}g(x) =b}$$ thì $$\displaystyle{\lim_{x \to a}f(g(x))}= f(\displaystyle{\lim_{x \to a}g(x)})= f(b)$$\

3. Factor and Cancel\
   $$\displaystyle{\lim_{x \to 2}\frac{x^2+4x-12}{x^2-2x}}= \displaystyle{\lim_{x \to 2}\frac{(x-2)(x+6)}{x(x-2)}}=\displaystyle{\lim_{x \to 2}\frac{x^2+4x-12}{x^2-2x}}= \displaystyle{\lim_{x \to 2}\frac{x+6}{x}}=\frac{8}{2}=4$$\

4. Rationalize Numerator/Denominator\
   $$\displaystyle{\lim_{x \to 2}\frac{x^2+4x-12}{x^2-2x}}= \displaystyle{\lim_{x \to 2}\frac{(x-2)(x+6)}{x(x-2)}}=\displaystyle{\lim_{x \to 2}\frac{x^2+4x-12}{x^2-2x}}= \displaystyle{\lim_{x \to 2}\frac{x+6}{x}}=\frac{8}{2}=4$$$$\displaystyle{\lim_{x \to 2}\frac{3-\sqrt{x}}{x^2-81}}= \displaystyle{\lim_{x \to 2}\frac{3-\sqrt{x}}{x^2-81} \frac{3+\sqrt{x}}{3+\sqrt{x}}}=\displaystyle{\lim_{x \to 2}\frac{9-x}{(x^2-81)(3+\sqrt{x})}}=\displaystyle{\lim_{x \to 2}\frac{1}{(x+9)(3+\sqrt{x})}}=\frac{-1}{(18)(6)}=-\frac{1}{108}$$\

5. Combine Rational Expressions\
   $$\displaystyle{\lim_{h \to 0}\frac{1}{h}(\frac{1}{x+h}-\frac{1}{x})}=\displaystyle{\lim_{h \to 0}\frac{1}{h}(\frac{x-(x+h)}{x(x+h)})}=\displaystyle{\lim_{h \to 0}\frac{1}{h}(\frac{-h}{x(x+h)})}=\displaystyle{\lim_{h \to 0}(\frac{-1}{x(x+h)})}=-\frac{1}{x^2}$$\

6. L'Hospital's Rule\
   Nếu $$\displaystyle{\lim_{x \to a}\frac{f(x)}{g(x)}=\frac{0}{0}}$$ hoặc $$\displaystyle{\lim_{x \to a}\frac{f(x)}{g(x)}=\frac{+\infin}{-\infin}}$$ \
   \
   Thì  $$\displaystyle{\lim_{x \to a}\frac{f(x)}{g(x)}=\lim_{x \to a}\frac{f'(x)}{g'(x)}}$$ a là một số thực, $$\infin$$ hoặc $$-\infin$$\

7. Polynomials at Infinity\
   p(x) và q(x)  là đa thức. Để tính $$\displaystyle{\lim_{x \to \pm \infin}\frac{p(x)}{q(x)}}$$ ta đưa hệ số nhân lớn nhất của x trong q(x) ra ngoài làm nhân tử chung của cả hai q(x) và p(x) xong rồi tím giới hạn\
   \
   $$\displaystyle{\lim_{x \to - \infin} \frac{3x^2-4}{5x-2x^2}}= \displaystyle{\lim_{x \to - \infin}\frac{x^2(3-\frac{4}{x^2})}{x^2(\frac{5}{x}-2)}}=\displaystyle{\lim_{x \to - \infin}\frac{3-\frac{4}{x^2}}{\frac{5}{x}-2}}= -\frac{3}{2}$$\

8. Piecewise Function\
   $$\displaystyle{\lim_{x\to -2}g(x)}$$ tại  $$g(x)= \begin{cases}    x^2+5 & x < -2 \\   1-3x & t\geq 2  \end{cases}$$\
   \
   Tính 2 phía giới hạn\
   $$\displaystyle{\lim_{x\to -2^-}g(x)} =\displaystyle{\lim_{x\to -2^-} x^2+5}=9$$\
   \
   $$\displaystyle{\lim_{x\to -2^+} g(x)} =\displaystyle{\lim_{x\to -2^+} 1-3x}=7$$\
   \
   Giới hạn của mỗi mặt là khác nhau nên $$\displaystyle{\lim_{x\to -2}g(x)}$$ không xuất hiện. Nếu cả hai mặt của giới hạn bằng nhau thì $$\displaystyle{\lim_{x\to -2}g(x)}$$ mới có thể xuất hiện và có cùng một giá trị\

9.  Some Continuous Functions\
    Một phần danh sách của các hàm liên tục và các giá trị của x mà chúng liên tục

    1. Đa thức cho tất cả x
    2. Hàm phân thức, ngoại trừ x được tạo bằng cách chia cho 0
    3. $$\sqrt[n]{x} (\text{n odd})$$ cho tất cả x
    4. $$\sqrt[n]{x}(\text{n even})$$cho tất cả $$x\geqslant 0$$.
    5. $$e^x$$ cho tất cả x.
    6. $$ln$$ x cho x > 0.
    7. cos(x) và sin(x) cho tất cả x
    8. tan(x)  và sec(x) với $$x \ne..., -\frac{3\pi}{2},-\frac{\pi}{2},\frac{\pi}{2},\frac{3\pi}{2},...$$
    9. cot(x) và csc(x) với $$x\ne ..., -2\pi, -\pi, 0, \pi, 2\pi,...$$


10. Intermediate value Theorem\
    Giả sử rằng f(x) là liên tục trên \[a,b] và đặt m là bất kỳ số nào giữa f(a) và f(b). Thì tồn tại một số c sao cho a < c < b và f(c) =M



## 2. Đạo hàm

### 2.1 Định nghĩa và ký hiệu&#x20;

Nếu $$y=f(x)$$ thì đạo hàm được xác định là $$f'(x)= \displaystyle{\lim_{h \to 0} \frac{f(x+h)-f(x)}{h}}$$\
\
Nếu $$y=f(x)$$ thì tất cả các ký hiệu tương đương sau đây đều cho đạo hàm:\
\
$$f'(x) = y' =\frac{df}{dx}  \frac{dy}{dx}=\frac{d}{dx}(f(x))=Df(x)$$\
\
Nếu $$y=f(x)$$ thì tất cả các ký hiệu cho đạo hàm sau đây được đánh giá tại x=a\
\
$$f'(x) = y'|_{x=a}= \frac{df}{dx} |_{x=a}=\frac{dy}{dx}|_{x=a}=Df(a)$$



### 2.2 Giải thích đạo hàm

Nếu $$y=f(x)$$ thì,

1. $$m=f'(a)$$ là độ dốc của đường tiếp tuyến với $$y= f(x)$$ tại x = a được cho bởi $$y=f(a) +f'(a)(x-a).$$\

2. $$f'(a)$$  sự thay đổi tức thời của $$f(x)$$ tại x = a.
3. Nếu $$f(x)$$ là một vị trí của một đối tượng tại một thời điểm x thì $$f'(a)$$ là vận tốc của đối tượng đó tại x=a

### 2.3  Các tính chất và công thức cơ bản

Nếu $$f(x)$$ và $$g(x)$$ là các hàm khác biệt ( đạo hàm có tồn tại) , c và n là số thực bất kỳ nào.

1. $$(cf)'= cf'(x)$$
2. $$(f\pm g)'= f'(x)\pm g'(x)$$
3. $$(fg)' = f'g+fg'- \text{Product Rule}$$
4. $$(\frac{f}{g})'=\frac{f'g-fg'}{g^2}- \text{Quotient Rule}$$
5. $$\frac{d}{dx}(c)=0$$
6. $$\frac{d}{dx}(x^n)=nx^{n-1}- \text{Power Rule}$$
7. $$\frac{d}{dx}(f(g(x)))= f'(g(x))g'(x)$$\
   \
   Đây là một Quy tắc chuỗi

### 2.4 Đạo hàm thường gặp

<table data-header-hidden><thead><tr><th width="240"></th><th width="239"></th><th></th></tr></thead><tbody><tr><td><span class="math">\frac{d}{dx}(x)=1</span></td><td><span class="math">\frac{d}{dx}(\csc x)= - \csc x \cot x</span></td><td><span class="math">\frac{d}{dx}(a^x)=a^x\ln(a)</span></td></tr><tr><td><span class="math">\frac{d}{dx}(\sin x)=\cos x</span></td><td><span class="math">\frac{d}{dx} (\cot x) = - \csc^2 x</span></td><td><span class="math">\frac{d}{dx}(e^x)=e^x</span></td></tr><tr><td><span class="math">\frac{d}{dx}(\cos x)= -\sin x</span></td><td><span class="math">\frac{d}{dx} (\sin^{-1} x)= \frac{1}{\sqrt{1-x^2}}</span></td><td><span class="math">\frac{d}{dx}(\ln(x))=\frac{1}{x},x>0</span></td></tr><tr><td><span class="math">\frac{d}{dx}\tan x= \sec^2 x</span></td><td><span class="math">\frac{d}{dx}(\cos^{-1}x) = -\frac{1}{\sqrt{1-x^2}}</span></td><td><span class="math">\frac{d}{dx}(\ln|x|)= \frac{1}{x},x\ne0</span></td></tr><tr><td><span class="math">\frac{d}{dx}(\sec x) = \sec x \tan x</span></td><td><span class="math">\frac{d}{dx}(\tan^{-1}x)= \frac{1}{1+x^2}</span></td><td><span class="math">\frac{d}{dx}(\log_a(x))=\frac{1}{x\ln a} \text{ , }x > 0</span></td></tr></tbody></table>



### 2.5 Biến thể quy tắc chuỗi

| $$\frac{d}{dx}([f(x)]^n)= n[f(x)]^{n-1}f'(x)$$ | $$\frac{d}{dx}(cos[f(x)])= - f'(x)\sin[f(x)]$$             |
| ---------------------------------------------- | ---------------------------------------------------------- |
| $$\frac{d}{dx}(e^{f(x)})= f'(x)e^{f(x)}$$      | $$\frac{d}{dx}(tan[f(x)])= f'(x)\sec^2[f(x)]$$             |
| $$\frac{d}{dx}()\ln[f(x)]=\frac{f'(x)}{f(x)}$$ | $$\frac{d}{dx}(\sec[f(x)])= f'(x)\sec[f(x)]\tan[f(x)]$$    |
| $$\frac{d}{dx} (sin[f(x)])$$                   | $$\frac{d}{dx}(tan^{-1}[f(x)])= \frac{f'(x)}{1+[f(x)]^2}$$ |



### 2.6  Đạo hàm bậc cao&#x20;

Đạo hàm bậc hai được ký hiệu là $$f''(x) =f^{(2)}(x) = \frac{d^2f}{dx^2}$$ và được định nghĩa là $$f''(x)= (f'(x))'$$, i.e.  đạo hàm của đạo hàm đầu tiên , $$f'(x)$$



Đạo hàm bậc n được ký hiệu là $$f^{(n)}(x) = \frac{d^nf}{dx^n}$$ và được định nghĩa là $$f^{(n)}(x)= (f^{n-1}(x))'$$ , i.e đạo hàm của đạo hàm thứ (n-1), $$f^{(n-1)}(x)$$



### 2.7  Tăng / giảm - Lõm lên / Lõm xuống

**Điểm quan trọng:**

**x = c là một điểm quan trọng của** $$f(x)$$ được cung cấp khi&#x20;

1. $$f'(c) =0$$
2. $$f'(c)$$ không tồn tại

**Tăng / giảm:**  &#x20;

1. Nếu $$f'(x)>0$$ cho tất cả x trong một khoảng I thì $$f(x)$$ sẽ tăng trong khoảng thời gian I
2. Nếu $$f'(x)<0$$ cho tất cả x trong một khoảng I thì $$f(x)$$ sẽ giảm trong khoảng thời gian I
3. Nếu $$f'(x)=0$$ cho tất cả x trong một khoảng I thì $$f(x)$$ sẽ giữ nguyên trong khoảng thời gian I



**Lõm lên/ Lõm xuống:**

1. Nếu $$f''(x)>0$$ cho tất cả x trong một khoảng I thì $$f(x)$$ lõm lên vào khoảng I&#x20;
2. Nếu $$f''(x)<0$$ cho tất cả x trong một khoảng I thì $$f(x)$$ lõm xuống vào khoảng I&#x20;

**Điểm uốn:**

x = c là một điểm uốn của $$f(x)$$ nếu độ lõm thay đổi tại x = c



## 3. Tích phân&#x20;

### 3.1 Định nghĩa

Definite Integral: Giả sử $$f(x)$$ liên tục trên $$[a,b]$$. Chia $$[a,b]$$ thành n tập con có chiều rộng $$\Delta x$$ và chọn $$x_i^*$$ từ mỗi khoảng. Ta được

$$
\displaystyle \int_{a}^{b} f(x) dx=\displaystyle{\lim \sum_{i=1}^n f(x_i^*)\Delta x}
$$



**Anti-Derivative(Nguyên hàm):**  Nguyên hàm của $$f(x)$$ là một hàm , $$F(x)$$ sao cho $$F'(x)= f(x)$$



**Indefinite Integral (Tích phân không xác định):** $$\displaystyle{\int f(x) dx}= F(x)+c$$ khi $$F(x)$$ là một nguyên hàm của $$f(x)$$



### 3.2  Định lý cơ bản của giải tích

**Part I:**

Nếu $$f(x)$$ liên tục trên $$[a,b]$$ thì $$g(x)= \displaystyle{\int_a^x f(t)dt}$$ \
thì cũng liên tục trên $$[a,b]$$ và $$g'(x)=\frac{d}{dx} \displaystyle{\int_a^x f(t)dt}=f(x)$$



**Part II:**

$$f(x)$$ liên tục trên $$[a,b]$$, $$F(x)$$ là một nguyên hàm của $$f(x)$$ (i.e. $$F(x)=\displaystyle{\int f(x)dx}$$)

Thì : $$g'(x) =\frac{d}{dx}\displaystyle{\int_a^x f(t)dt =f(x)}$$



**Biến thể của Part I:**\
$$\frac{d}{dx}\displaystyle{\int_a^{u(x)}f(t)dt}=u'(x)f[u(x)]$$\
\
$$\frac{d}{dx}\displaystyle{\int_{vx}^{b}f(t)dt}=-v'(x)f[v(x)]$$\
\
$$\frac{d}{dx}\displaystyle{\int_{v(x)}^{u(x)}f(t)dt}=u'(x)f[u(x)]- v'(x)f[v(x)]$$



### 3.3 Tính chất

<table data-header-hidden data-full-width="true"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><span class="math">\displaystyle{\int}f(x) \pm g(x)dx= \displaystyle{\int}f(x)dx\pm \displaystyle{\int}g(x)dx</span></td><td><span class="math">\displaystyle{\int}cf(x)dx=c\displaystyle{\int_a^b}f(x)dx</span> , c là một hằng số</td></tr><tr><td><span class="math">\displaystyle{\int_a^b}f(x) \pm g(x)dx= \displaystyle{\int_a^b}f(x)dx\pm \displaystyle{\int_a^b}g(x)dx</span></td><td><span class="math">\displaystyle{\int_a^b}cf(x)dx=c\displaystyle{\int_a^b}f(x)dx</span>, c là một hằng số<span class="math">f(x) = x * e^{2 pi i \xi x}</span></td></tr><tr><td><span class="math">\displaystyle{\int_a^a}f(x)dx=0</span></td><td><span class="math">\displaystyle{\int_a^b}cdx=c(b-a)</span></td></tr><tr><td><span class="math">\displaystyle{\int_a^b}f(x)dx=-\displaystyle{\int_b^a}f(x)dx</span></td><td><span class="math">\displaystyle{|\int_a^af(x)dx|}\leq \displaystyle{\int_a^a}|f(x)|dx</span></td></tr><tr><td><span class="math">\displaystyle{\int_a^b}f(x)dx=\displaystyle{\int_a^c}f(x)dx+\displaystyle{\int_c^b}f(x)dx</span> với mỗi giá trị của c</td><td></td></tr></tbody></table>

<table data-header-hidden data-full-width="true"><thead><tr><th></th></tr></thead><tbody><tr><td>Nếu <span class="math">f(x)\ge g(x) </span> trong khoảng <span class="math">a\le x\le b</span> thì <span class="math">\displaystyle{\int_a^b}f(x)dx \ge\displaystyle{\int_a^b}g(x)dx</span></td></tr><tr><td>Nếu <span class="math">f(x) \ge 0</span> trong khoảng <span class="math">a \le x\le b</span> thì <span class="math">\displaystyle{\int_a^b}f(x)dx\ge 0</span></td></tr><tr><td>Nếu <span class="math">m \le f(x)\le M</span> trong khoảng <span class="math">a\le x\le b</span> thì <span class="math">m(b-a)\le \displaystyle{\int_a^b}f(x)dx \le M(b-a)</span></td></tr></tbody></table>

### 3.4 Tích phân thông thường

<table data-header-hidden data-full-width="true"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><span class="math">\displaystyle{\int}k dx= kx+c</span></td><td><span class="math">\displaystyle{\int}\sec^2udu=\tan u +c</span></td></tr><tr><td><span class="math">\displaystyle{\int}x^ndx= \frac{1}{n+1}x^{n+1}+c. n\ne -1</span></td><td><span class="math">\displaystyle{\int} \sec u  \tan u du =\sec u+c</span></td></tr><tr><td><span class="math">\displaystyle{\int}x^{-1} dx= \displaystyle{\int}\frac{1}{x}dx= \ln|x|+c</span></td><td><span class="math">\displaystyle{\int} \csc u \cot udu= -\csc u +c</span></td></tr><tr><td><span class="math">\displaystyle{\int} \frac{1}{ax+b}dx=\frac{1}{z}\ln |ax+b|+c</span></td><td><span class="math">\displaystyle{\int}\csc^2udu =- \cot u +c</span></td></tr><tr><td><span class="math">\displaystyle{\int}\ln udu =u\ln (u)-u+c</span></td><td><span class="math">\displaystyle{\int}\tan u du= \ln |\sec u|+c</span></td></tr><tr><td><span class="math">\displaystyle{\int}e^udu=u\ln (u)-u+c</span></td><td><span class="math">\displaystyle{\int} \sec u du=\ln |\sec u +\tan u|+c</span></td></tr><tr><td><span class="math">\displaystyle{\int}\cos udu=\sin u +c</span> </td><td><span class="math">\displaystyle{\int}\frac{1}{a^2+u^2}du=\frac{1}{a}\tan^{-1} (\frac{u}{a})+c</span></td></tr><tr><td><span class="math">\displaystyle{\int}\sin u du= -\cos u+c</span></td><td><span class="math">\displaystyle{\int}\frac{1}{a^2-u^2}du=\sin^{-1} (\frac{u}{a})+c</span></td></tr></tbody></table>



### 3.5  Kỹ thuật tích phân tiêu chuẩn

> Note: tại nhiều trường học sẽ dạy toàn bộ kỹ thuật trong sách giải tích 2 ngoại trừ Substitution Rule

**u Substitution**: Sự thay thế $$u=g(x)$$ sẽ chuyển đổi $$\displaystyle{\int} f(g(x))g'(x)dx= \displaystyle{\int _{g(a)}^{g(b)}}f(u)du$$ sử dụng $$du=g'(x)dx$$. Đối với các tích phân không xác định, hãy bỏ các giới hạn của tích hợp



Ex:&#x20;

$$\displaystyle{\int_1^2}5x^2\cos(x^3)dx$$\
\
$$u=x^3 \to du=3x^2dx \to x^2dx=\frac{1}{3}du$$\
\
$$x= 1 \to u=1^3=1:: x=2\to u=2^3=8$$



**Tích phân từng phân:**

**a** $$\displaystyle{\int}udv=uv-\displaystyle{\int}vdu$$ và $$\displaystyle{\int_a^b}u dv=uv|_a^b- \displaystyle{\int_a^b}vdu$$. Chọn u và dv trong tích phân và tính du bằng cách phân bieejjt u và tính toán v sử dụng $$v=\displaystyle{\int}dv$$

Ex: $$\displaystyle{\int} xe^{-x }dx$$\
\
$$u=x$$  $$dv=e^{-x} \to du|=dx$$  $$v=-e^{-x}$$\
\
$$\displaystyle \int xe^{-x}dx= -xe^{-x}+ \int e^{-x} dx = -xe^{-x}-e^{-x}+c$$











