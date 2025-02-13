# Java - Exception Handling

## 1. Exception

Trong Java, **Exception** là một đối tượng biểu thị các tình huống bất thường hoặc lỗi xảy ra trong quá trình thực thi chương trình. Khi một exception được "ném" (throw), nó sẽ làm gián đoạn luồng thực thi thông thường và chuyển quyền điều khiển đến khối lệnh xử lý lỗi (ví dụ: khối `catch`).

### Các loại Exception

* **Checked Exceptions:**\
  Đây là những exception được kiểm tra tại thời điểm biên dịch. Bạn buộc phải xử lý chúng bằng cách sử dụng khối `try-catch` hoặc khai báo phương thức với `throws`. Ví dụ: `IOException`, `SQLException`.
* **Unchecked Exceptions:**\
  Bao gồm `RuntimeException` và các lớp con của nó, thường phát sinh do lỗi logic trong chương trình (như `NullPointerException`, `ArithmeticException`). Chúng không bắt buộc phải được xử lý tại thời điểm biên dịch.

<figure><img src="../../.gitbook/assets/image (17).png" alt="Hierarchy of Java Exception classes" width="563"><figcaption><p><a href="https://medium.com/@rushilakade66/hierarchy-of-java-exception-classes-eb90c5112a02">https://medium.com/@rushilakade66/hierarchy-of-java-exception-classes-eb90c5112a02</a></p></figcaption></figure>

Exception giúp chương trình có thể xử lý các lỗi một cách có kiểm soát thay vì để chương trình bị dừng đột ngột. Khi một exception xảy ra, bạn có thể ghi log, hiển thị thông báo lỗi, hoặc thực hiện các hành động khắc phục để chương trình tiếp tục chạy một cách an toàn.

## 2. Try-catch block

**Try-catch block** trong Java là một cấu trúc được sử dụng để xử lý các exception (ngoại lệ) xảy ra trong quá trình thực thi của chương trình. Cấu trúc này cho phép bạn “bắt” lỗi và xử lý chúng một cách có kiểm soát, thay vì để chương trình dừng đột ngột.

### Cấu trúc cơ bản của Try-catch block:

```java
try {
    // Khối lệnh có khả năng gây ra exception
} catch (ExceptionType e) {
    // Khối lệnh xử lý exception khi nó được ném ra
} finally {
    // (Tùy chọn) Khối lệnh này luôn được thực thi, dù có exception hay không
}
```

### Chi tiết các thành phần:

1. **try block:**
   * Chứa đoạn mã có khả năng gây ra ngoại lệ.
   * Nếu một exception xảy ra trong khối này, luồng thực thi sẽ chuyển ngay đến khối catch tương ứng.
2. **catch block:**
   * Được sử dụng để “bắt” và xử lý các ngoại lệ cụ thể được ném ra từ khối try.
   * Bạn có thể có nhiều khối catch để xử lý các loại exception khác nhau.
   *   Ví dụ:

       ```java
       try {
           // Một đoạn mã có thể gây ra exception
           int result = 10 / 0;
       } catch (ArithmeticException e) {
           System.out.println("Lỗi: Chia cho 0 không hợp lệ!");
       }
       ```
3. **finally block (tùy chọn):**
   * Đoạn mã trong khối finally luôn được thực thi, cho dù exception có xảy ra hay không.
   * Thường được sử dụng để giải phóng tài nguyên, đóng file, kết nối cơ sở dữ liệu, v.v.
   *   Ví dụ:

       ```java
       try {
           // Đoạn mã có khả năng gây ra exception
       } catch (Exception e) {
           // Xử lý exception
       } finally {
           // Thực hiện dọn dẹp tài nguyên
           System.out.println("Khối finally luôn được thực hiện.");
       }
       ```

#### Ví dụ đầy đủ:

```java
public class TryCatchExample {
    public static void main(String[] args) {
        try {
            int a = 10, b = 0;
            int result = a / b; // Gây ra ArithmeticException vì chia cho 0
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Lỗi: Không thể chia cho 0!");
        } finally {
            System.out.println("Khối finally luôn được thực hiện dù có exception hay không.");
        }
    }
}
```

