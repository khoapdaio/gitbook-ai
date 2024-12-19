# 🔤 Ký Hiệu Toán học

## Latex

LaTeX là một hệ thống soạn thảo tài liệu nổi bật với khả năng tạo ra các ký hiệu toán học chính xác. Nó cho phép biểu diễn các công thức phức tạp như phân số $$\frac{a}{b}$$, tổng $$(a+b=c)$$ , và tích phân, nó là công cụ quan trọng trong các lĩnh vực khoa học và kỹ thuật.

Dưới đây là các ký hiệu toán học viết dưới dạng latex &#x20;

### Số học

| Notation                         | Example                                                                                                                     | Inline                                                                                                            | Code Block                                                            |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Addition                         | a+b                                                                                                                         | `$a+b$`                                                                                                           | <p><code>$$</code><br><code>a+b</code><br><code>$$</code></p>         |
| Subtraction                      | a−b                                                                                                                         | `$a-b$`                                                                                                           | <p><code>$$</code><br><code>a-b</code><br><code>$$</code></p>         |
| Various Forms of Multiplication  | <p>a×b<br>a∗b<br>a⋅b</p>                                                                                                    | <p><code>$a \times b$</code><br><code>$a \ast b$</code><br><code>$a \cdot b$</code></p>                           | <p><code>$$</code><br><code>a \cdot b</code><br><code>$$</code></p>   |
| Various Forms of Division        | <p>a:b<br>a/b<br>a÷b<br>ab</p>                                                                                              | <p><code>$a \colon b$</code><br><code>$a / b$</code><br><code>$a \div b$</code><br><code>$\frac{a}{b}$</code></p> | <p><code>$$</code><br><code>a \div b</code><br><code>$$</code></p>    |
| Remainder / Modulo               | 5 mod 2 = 1                                                                                                                 | `$5\mod 2=1$`                                                                                                     | <p><code>$$</code><br><code>5\mod 2=1</code><br><code>$$</code></p>   |
| Negative Value                   | −a                                                                                                                          | `$-a$`                                                                                                            | <p><code>$$</code><br><code>-a</code><br><code>$$</code></p>          |
| Plus or Minus, Minus or Plus     | <p>±a<br>∓a</p>                                                                                                             | <p><code>$\pm a$</code><br><code>$\mp a$</code></p>                                                               | <p><code>$$</code><br><code>\pm a</code><br><code>$$</code></p>       |
| Squared, Cubed, nth-Power        | <p><span class="math">a^2</span><br><span class="math">a^3</span><br><span class="math">a^n</span></p>                      | <p><code>$a^2$</code><br><code>$a^3$</code><br><code>$a^n$</code></p>                                             | <p><code>$$</code><br><code>a^3</code><br><code>$$</code></p>         |
| Square Root, Cube Root, nth-Root | <p><span class="math">\sqrt{a}</span><br><span class="math">\sqrt[3]{a}</span><br><span class="math">\sqrt[n]{a}</span></p> | <p><code>$\sqrt{a}$</code><br><code>$\sqrt[3]{a}$</code><br><code>$\sqrt[n]{a}$</code></p>                        | <p><code>$$</code><br><code>\sqrt[3]{a}</code><br><code>$$</code></p> |

### Equality

<table data-full-width="false"><thead><tr><th>Notation</th><th>Example</th><th>Inline</th><th>Code Block</th></tr></thead><tbody><tr><td>Equals</td><td>3=1+23=1+2</td><td><code>$3=1+2$</code></td><td><code>$$</code><br><code>3=1+2</code><br><code>$$</code></td></tr><tr><td>Not Equals</td><td>3≠43=4</td><td><code>$3\neq4$</code></td><td><code>$$</code><br><code>3\neq4</code><br><code>$$</code></td></tr><tr><td>Identical / Equivalent To</td><td>a≡ba≡b</td><td><code>$a \equiv b$</code></td><td><code>$$</code><br><code>a \equiv b</code><br><code>$$</code></td></tr><tr><td>Proportional To</td><td>a∝ba∝b</td><td><code>$a \propto b$</code></td><td><code>$$</code><br><code>a \propto b</code><br><code>$$</code></td></tr><tr><td>Approximately Equal To</td><td>sin⁡(0.01)≈0.01sin(0.01)≈0.01</td><td><code>$\sin(0.01) \approx 0.01$</code></td><td><code>$$</code><br><code>\sin(0.01) \approx 0.01</code><br><code>$$</code></td></tr></tbody></table>

### So sánh

<table><thead><tr><th width="260">Notation</th><th>Example</th><th width="149">Inline</th><th>Code Block</th></tr></thead><tbody><tr><td>a Less Than b<br>a Greater Than b</td><td>a&#x3C;b<br>a>b</td><td><code>$a&#x3C;b$</code><br><code>$a>b$</code></td><td><code>$$</code><br><code>a&#x3C;b</code><br><code>$$</code></td></tr><tr><td>a Less Than or Equal To b<br>a Greater Than or Equal To b</td><td>a≤b<br>a≥b</td><td><code>$a \leq b$</code><br><code>$a \geq b$</code></td><td><code>$$</code><br><code>a \leq b</code><br><code>$$</code></td></tr><tr><td>a Much Smaller Than b<br>a Much Larger Than b</td><td>a≪b<br>a≫b</td><td><code>$a \ll b$</code><br><code>$a \gg b$</code></td><td><code>$$</code><br><code>a \ll b</code><br><code>$$</code></td></tr></tbody></table>

### Đại số

| Notation               | Example                                                              | Inline                                                               | Code Block                                                                                                              |
| ---------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Factorial              | 5!=5×4×3×2×1                                                         | `$5!=5 \times 4 \times 3 \times 2 \times 1$`                         | <p><code>$$</code><br><code>5!=5 \times 4 \times 3 \times 2 \times 1</code><br><code>$$</code></p>                      |
| Absolute Value         | ∣−5∣=5                                                               | `$\|-5\|=5$`                                                         | <p><code>$$</code><br><code>|-5|=5</code><br><code>$$</code></p>                                                        |
| Function Of            | f(x)=2x2                                                             | `$f(x)=2x^2$`                                                        | <p><code>$$</code><br><code>f(x)=2x^2</code><br><code>$$</code></p>                                                     |
| Change or Difference   | Δx=x1−x0​                                                            | `$\Delta x = x_1 - x_0$`                                             | <p><code>$$</code><br><code>\Delta x = x_1 - x_0</code><br><code>$$</code></p>                                          |
| Pi                     | π=3.14159…                                                           | `$\pi = 3.14159...$`                                                 | <p><code>$$</code><br><code>\pi</code><br><code>$$</code></p>                                                           |
| Euler’s Constant       | e=2.71828…                                                           | `$e = 2.71828...$`                                                   | <p><code>$$</code><br><code>e = 2.71828...</code><br><code>$$</code></p>                                                |
| Sum                    | $$\displaystyle\sum_{k=3}^5 k^2=3^2 + 4^2 + 5^2 =50$$                | `$\displaystyle\sum_{k=3}^5 k^2=3^2 + 4^2 + 5^2 =50$`                | <p><code>$$</code><br><code>\displaystyle\sum_{k=3}^5 k^2=3^2 + 4^2 + 5^2 =50</code><br><code>$$</code></p>             |
| Series Product         | $$\displaystyle\prod_{x=2}^4 x^2 = 2^2 \times 3^2 \times 4^2 = 576$$ | `$\displaystyle\prod_{x=2}^4 x^2 = 2^2 \times 3^2 \times 4^2 = 576$` | <p><code>$$</code><br><code>\displaystyle\sum_{k=2}^4 k^2=2^2 \times 3^2 \times 4^2 = 576</code><br><code>$$</code></p> |
| Brackets & Parentheses | \[…]\(…)                                                             | `$[\ldots] (\ldots)$`                                                | <p><code>$$</code><br><code>[\ldots] (\ldots)</code><br><code>$$</code></p>                                             |

### Góc (Angles)

| Notation                 | Example    | Inline                     | Code Block                                                                       |
| ------------------------ | ---------- | -------------------------- | -------------------------------------------------------------------------------- |
| Angle                    | ∠          | `$\angle$`                 | <p><code>$$</code><br><code>\angle</code><br><code>$$</code></p>                 |
| Degree, Arc Min, Arc Sec | 30°45′30′′ | `$30\degree45\rq30\rq\rq$` | <p><code>$$</code><br><code>30\degree45\rq30\rq\rq</code><br><code>$$</code></p> |
| Radians                  | 360°=2πrad | `$360\degree = 2\pi rad$`  | <p><code>$$</code><br><code>360\degree = 2\pi rad</code><br><code>$$</code></p>  |

### Xác suất & Thống kê

| Notation                       | Example                                    | Inline                                     | Code Block                                                                                       |
| ------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| Probability of Event A         | P(A) or Pr⁡(A)                             | `$P(A)$ or $\Pr(A)$`                       | <p><code>$$</code><br><code>P(A)</code><br><code>$$</code></p>                                   |
| Intersection Prob. of A & B    | P(A∩B)                                     | `$P(A \cap B)$`                            | <p><code>$$</code><br><code>P(A \ca pB)</code><br><code>$$</code></p>                            |
| Union Prob. of A or B          | P(A∪B)                                     | `$P(A \cup B)$`                            | <p><code>$$</code><br><code>P(A \cup B)</code><br><code>$$</code></p>                            |
| Conditional Prob. of A Given B | P(A∣B)                                     | `$P(A\|B)$`                                | <p><code>$$</code><br><code>P(A|B)</code><br><code>$$</code></p>                                 |
| Median                         | $$\tilde{x}$$                              | `$\tilde{x}$`                              | <p><code>$$</code><br><code>\tilde{x}</code><br><code>$$</code></p>                              |
| Population Mean                | $$\mu , \overline{x} , \langle x \rangle$$ | `$\mu , \overline{x} , \langle x \rangle$` | <p><code>$$</code><br><code>\mu , \overline{x} , \langle x \rangle</code><br><code>$$</code></p> |
| Standard Deviation             | $$\sigma$$                                 | `$\sigma$`                                 | <p><code>$$</code><br><code>\sigma</code><br><code>$$</code></p>                                 |
| Varience                       | $$\sigma^2$$                               | `$\sigma^2$`                               | <p><code>$$</code><br><code>\sigma^2</code><br><code>$$</code></p>                               |

### Linear Algebra

#### Vector



<table><thead><tr><th>Notation</th><th width="161">Example</th><th>Inline</th><th>Code Block</th></tr></thead><tbody><tr><td>Vectors</td><td><span class="math">\mathbf{v}\overline{v}\vec{v}</span></td><td><code>$\mathbf{v}\overline{v}\vec{v}$</code></td><td><code>$$</code><br><code>\mathbf{v} \overline{v} \vec{v}</code><br><code>$$</code></td></tr><tr><td>Row Vector</td><td><span class="math">v=\begin{pmatrix}1&#x26;2&#x26;3\end{pmatrix}</span></td><td><code>$v=\begin{pmatrix}1&#x26;2&#x26;3\end{pmatrix}$</code></td><td><code>$$</code><br><code>v = \begin{pmatrix}</code><br><code>1 &#x26; 2 &#x26; 3</code><br><code>\end{pmatrix}</code><br><code>$$</code></td></tr><tr><td>Column Vector</td><td><span class="math">w=\begin{pmatrix}4\cr5\cr6\cr\end{pmatrix}</span></td><td><code>$w=\begin{pmatrix}4\cr5\cr6\cr\end{pmatrix}$</code></td><td><code>$$</code><br><code>w=\begin{pmatrix}</code><br><code>4 \cr</code><br><code>5 \cr</code><br><code>6 \cr</code><br><code>\end{pmatrix}</code><br><code>$$</code></td></tr><tr><td>Dot Product</td><td><span class="math">\mathbf{v} \cdot \mathbf{w}</span><br><span class="math">(v,w)</span><br><span class="math">\mathbf{v} \cdot \mathbf{w}$&#x3C;br>$(v,w)$&#x3C;br>$\left&#x3C;v | w\right></span><span class="math">\left&#x3C;v | w\right></span></td><td><code>$\mathbf{v} \cdot \mathbf{w}$&#x3C;br>$(v,w)$&#x3C;br>$\left&#x3C;v | w\right>$</code></td><td><code>$$</code><br><code>\mathbf{v}\cdot\mathbf{w}</code><br><code>(v,w)</code><br><code>\left&#x3C;v|w \right></code><br><code>$$</code></td></tr><tr><td>Cross Product</td><td><span class="math">v \times w</span></td><td><code>$v \times w$</code></td><td><code>$$</code><br><code>v \times w</code><br><code>$$</code></td></tr><tr><td>Length of v</td><td><span class="math">|v|</span></td><td><code>$|v|$</code></td><td><code>$$</code><br><code>|v|</code><br><code>$$</code></td></tr><tr><td>Norm of v</td><td><span class="math">||v||</span></td><td><code>$||v||$</code></td><td><code>$$</code><br><code>||v||</code><br><code>$$</code></td></tr></tbody></table>

#### Matric

| Notation                                          | Example                                                                     | Inline                                                | Code Block                                                                                                                                                                                             |
| ------------------------------------------------- | --------------------------------------------------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Matrix, 2 By 3                                    | $$A=\begin{bmatrix}1&2&3\cr4&5&6\end{bmatrix}$$                             | `$A=\begin{bmatrix}1&2&3\cr4&5&6\end{bmatrix}$`       | <p><code>$$</code><br><code>A=</code><br><code>\begin{bmatrix}</code><br><code>1 &#x26; 2 &#x26; 3 \cr</code><br><code>4 &#x26; 5 &#x26; 6</code><br><code>\end{bmatrix}</code><br><code>$$</code></p> |
| Product                                           | $$A \cdot B$$                                                               | `$A \cdot B$`                                         | <p><code>$$</code><br><code>A \cdot B</code><br><code>$$</code></p>                                                                                                                                    |
| Hadamard Product                                  | $$A \circ B$$                                                               | `$A \circ B$`                                         | <p><code>$$</code><br><code>A \circ B</code><br><code>$$</code></p>                                                                                                                                    |
| Kronecker Product                                 | $$A \otimes B$$                                                             | `$A \otimes B$`                                       | <p><code>$$</code><br><code>A \otimes B</code><br><code>$$</code></p>                                                                                                                                  |
| Transposed Matrix                                 | $$A^T$$                                                                     | `$A^T$`                                               | <p><code>$$</code><br><code>A^T</code><br><code>$$</code></p>                                                                                                                                          |
| <p>Hermitian Matrix or<br>Conjugate Transpose</p> | <p><span class="math">A^\dag</span><br><span class="math">A^\ast</span></p> | <p><code>$A^\dag$</code><br><code>$A^\ast$</code></p> | <p><code>$$</code><br><code>A^\dag</code><br><code>A^\ast</code><br><code>$$</code></p>                                                                                                                |
| Inverse Matrix                                    | $$A^{-1}$$                                                                  | `$A^{-1}$`                                            | <p><code>$$</code><br><code>A^{-1}</code><br><code>$$</code></p>                                                                                                                                       |
| Determinant                                       | $$|A|$$                                                                     | `$\|A\|$`                                             | <p><code>$$</code><br><code>|A|</code><br><code>$$</code></p>                                                                                                                                          |
| Norm                                              | $$||A||$$                                                                   | `$\|\|A\|\|$`                                         | <p><code>$$</code><br><code>||A||</code><br><code>$$</code></p>                                                                                                                                        |

### Calculus <a href="#calculus" id="calculus"></a>

| Notation                                                   | Example                                                                      | Inline                                                 | Code Block                                                                               |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| <p>Example Function:<br>y=x24y=4x2​</p>                    | $$y = \frac{x^2}{4}$$                                                        | `$y = \frac{x^2}{4}$`                                  | <p><code>$$</code><br><code>y = \frac{x^2}{4}</code><br><code>$$</code></p>              |
| <p>Integration<br>(Limits: 1 to 4)</p>                     | $$A = \int_1^4 \frac{x^2}{x} dx$$                                            | `$A = \int_1^4 \frac{x^2}{x} dx$`                      | <p><code>$$</code><br><code>A = \int_1^4 \frac{x^2}{x} dx</code><br><code>$$</code></p>  |
| Differentiation                                            |                                                                              |                                                        |                                                                                          |
| <p>First Derivative<br>With Respect To xx</p>              | $$\frac{df}{dx}$$                                                            | `$\frac{df}{dx}$`                                      | <p><code>$$</code><br><code>\frac{df}{dx}</code><br><code>$$</code></p>                  |
| <p>Partial Derivative<br>With Respect To xx</p>            | $$\frac{\partial f}{\partial x}$$                                            | `$\frac{\partial f}{\partial x}$`                      | <p><code>$$</code><br><code>\frac{\partial f}{\partial x}</code><br><code>$$</code></p>  |
| <p>First and Second Derivative<br>of Function</p>          | <p><span class="math">f\rq</span><br><span class="math">f\rq\rq</span></p>   | <p><code>$f\rq$</code><br><code>$f\rq\rq$</code></p>   | <p><code>$$</code><br><code>f\rq</code><br><code>f\rq\rq</code><br><code>$$</code></p>   |
| <p>First and Second Derivative<br>With Respect To Time</p> | <p><span class="math">\dot f</span><br><span class="math">\ddot f</span></p> | <p><code>$\dot f$</code><br><code>$\ddot f$</code></p> | <p><code>$$</code><br><code>\dot f</code><br><code>\ddot f</code><br><code>$$</code></p> |

### Số phúc

| Notation                         | Example                                                                                       | Inline                                                                  | Block                                                                                                     |
| -------------------------------- | --------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Imaginary Unit ii                | $$z=3+2i$$                                                                                    | `$z=3+2i$`                                                              | <p><code>$$</code><br><code>z=3+2i</code><br><code>$$</code></p>                                          |
| Real Part Of Complex Number      | <p><span class="math">\Re(z)=3</span><br><span class="math">\operatorname{Re}(z)=3</span></p> | <p><code>$\Re(z)=3$</code><br><code>$\operatorname{Re}(z)=3$</code></p> | <p><code>$$</code><br><code>\Re(z)=3</code><br><code>\operatorname{Re}(z)=3</code><br><code>$$</code></p> |
| Imaginary Part Of Complex Number | <p><span class="math">\Im(z)=2</span><br><span class="math">\operatorname{Im}(z)=2</span></p> | <p><code>$\Im(z)=2$</code><br><code>$\operatorname{Im}(z)=2$</code></p> | <p><code>$$</code><br><code>\Im(z)=2</code><br><code>\operatorname{Im}(z)=2</code><br><code>$$</code></p> |
| Complex Conjugate                | $$\bar{z}=z^*=3-2i$$$$f(x) = x * e^{2 pi i \xi x}$$                                           | `$\bar{z}=z^*=3-2i$`                                                    | <p><code>$$</code><br><code>\bar{z}=z^*=3-2i</code><br><code>$$</code></p>                                |

#### Bảng chữ cái Greek

| Letter  | Lower | Inline       | Upper | Inline       |
| ------- | ----- | ------------ | ----- | ------------ |
| Alpha   | α     | `$\alpha$`   | A     | `$\Alpha$`   |
| Beta    | β     | `$\beta$`    | B     | `$\Beta$`    |
| Gamma   | γ     | `$\gamma$`   | Γ     | `$\Gamma$`   |
| Delta   | δ     | `$\delta$`   | Δ     | `$\Delta$`   |
| Epsilon | ϵ     | `$\epsilon$` | E     | `$\Epsilon$` |
| Zeta    | ζ     | `$\zeta$`    | Z     | `$\Zeta$`    |
| Eta     | η     | `$\eta$`     | H     | `$\Eta$`     |
| Theta   | θ     | `$\theta$`   | Θ     | `$\Theta$`   |
| Iota    | ι     | `$\iota$`    | I     | `$\Iota$`    |
| Kappa   | κ     | `$\kappa$`   | K     | `$\Kappa$`   |
| Lambda  | λ     | `$\lambda$`  | Λ     | `$\Lambda$`  |
| Mu      | μ     | `$\mu$`      | M     | `$\Mu$`      |
| Nu      | ν     | `$\nu$`      | N     | `$\Nu$`      |
| Xi      | ξ     | `$\xi$`      | Ξ     | `$\Xi$`      |
| Omicron | ο     | `$\omicron$` | O     | `$\Omicron$` |
| Pi      | π     | `$\pi$`      | Π     | `$\Pi$`      |
| Rho     | ρ     | `$\rho$`     | P     | `$\Rho$`     |
| Sigma   | σ     | `$\sigma$`   | Σ     | `$\Sigma$`   |
| Tau     | τ     | `$\tau$`     | T     | `$\Tau$`     |
| Upsilon | υ     | `$\upsilon$` | Υ     | `$\Upsilon$` |
| Phi     | ϕ     | `$\phi$`     | Φ     | `$\Phi$`     |
| Chi     | χ     | `$\chi$`     | X     | `$\Chi$`     |
| Psi     | ψ     | `$\psi$`     | Ψ     | `$\Psi$`     |
| Omega   | ω     | `$\omega$`   | Ω     | `$\Omega$`   |

