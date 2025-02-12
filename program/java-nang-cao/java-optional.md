# Java - Optional

`Optional` là một lớp container (hộp chứa) được giới thiệu từ Java 8, giúp quản lý giá trị có thể có hoặc không (tức là có thể là `null`). Mục đích chính của `Optional` là giúp tránh các lỗi NullPointerException bằng cách cung cấp một cách rõ ràng để xử lý trường hợp giá trị có thể không tồn tại.

Dưới đây là một số điểm chính về `Optional`:

## **1. Khái niệm cơ bản:**

* `Optional` chứa một giá trị nếu có, hoặc rỗng nếu không có giá trị.
* Thay vì sử dụng `null` để biểu thị sự vắng mặt của một giá trị, `Optional` cung cấp một cách an toàn hơn để xử lý tình huống này.

## **2. Lợi ích:**

* **Tránh NullPointerException:** Khi sử dụng `Optional`, bạn sẽ buộc phải xử lý trường hợp không có giá trị, từ đó giảm nguy cơ gặp phải lỗi null.
* **Mã rõ ràng và dễ hiểu:** Khi một phương thức trả về `Optional`, nó rõ ràng cho người đọc biết rằng kết quả có thể không có giá trị.
* **Các phương thức hỗ trợ:** `Optional` cung cấp nhiều phương thức hữu ích để thao tác và xử lý giá trị như `ifPresent()`, `orElse()`, `orElseGet()`, `map()`, `flatMap()`, v.v.

## **3. Các phương thức thường dùng:**

* **`Optional.of(T value)`:** Tạo một `Optional` chứa giá trị không null. Nếu giá trị truyền vào là `null` thì sẽ ném ngoại lệ `NullPointerException`.
* **`Optional.ofNullable(T value)`:** Tạo một `Optional` chứa giá trị nếu không phải null, ngược lại tạo ra một `Optional.empty()`.
* **`isPresent()`:** Kiểm tra xem `Optional` có chứa giá trị hay không.
* **`ifPresent(Consumer<? super T> consumer)`:** Nếu có giá trị, thực hiện hành động với giá trị đó.
* **`orElse(T other)`:** Trả về giá trị nếu có, nếu không thì trả về giá trị mặc định được cung cấp.
* **`orElseGet(Supplier<? extends T> supplier)`:** Tương tự như `orElse()`, nhưng nhận một `Supplier` để tạo giá trị mặc định khi cần.
* **`orElseThrow(Supplier<? extends X> exceptionSupplier)`:** Nếu không có giá trị, ném ngoại lệ được cung cấp.

## **4. Ví dụ minh họa:**

```java
import java.util.Optional;

public class OptionalExample {
    public static void main(String[] args) {
        // Tạo Optional từ một giá trị có thể null
        String name = null;
        Optional<String> optionalName = Optional.ofNullable(name);

        // Kiểm tra và in giá trị nếu có
        optionalName.ifPresent(n -> System.out.println("Name is: " + n));

        // Cung cấp giá trị mặc định nếu Optional rỗng
        String defaultName = optionalName.orElse("Default Name");
        System.out.println("Name: " + defaultName);

        // Sử dụng map để biến đổi giá trị nếu có
        Optional<Integer> nameLength = optionalName.map(String::length);
        nameLength.ifPresent(len -> System.out.println("Length of name: " + len));
    }
}
```

## **5.Khi nào nên sử dụng `Optional`:**

* **Trong các phương thức trả về:** Khi một phương thức có khả năng không tìm thấy kết quả, thay vì trả về `null`, bạn có thể trả về một `Optional` để buộc người dùng của phương thức phải xử lý trường hợp không có giá trị.
* **Xử lý các giá trị có thể null:** Giúp code trở nên an toàn hơn và tránh các lỗi do quên kiểm tra `null`.

***

**Tóm lại:**\
`Optional` trong Java là một công cụ hữu ích để xử lý các giá trị có thể không tồn tại một cách an toàn và rõ ràng, giúp giảm thiểu các lỗi liên quan đến `null` và cải thiện chất lượng code thông qua việc ép buộc kiểm tra giá trị trước khi sử dụng.
