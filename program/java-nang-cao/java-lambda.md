# Java -  Lambda

**Lambda** trong Java, hay còn gọi là **biểu thức lambda**, là một tính năng được giới thiệu từ Java 8. Nó cho phép bạn định nghĩa và sử dụng các hàm vô danh (anonymous functions) một cách ngắn gọn và trực quan. Dưới đây là một số điểm chính về lambda trong Java:

## **1. Biểu thức lambda là gì?**

Lambda là một biểu thức cho phép bạn viết một hàm không tên (anonymous function) mà có thể được truyền đi như một đối tượng. Điều này giúp giảm bớt boilerplate code khi làm việc với các interface chức năng (functional interfaces) – đó là các interface chỉ có một phương thức trừu tượng.

## **2.Cấu trúc của biểu thức lambda:**

* Một biểu thức lambda gồm có:
  * **Danh sách tham số**: Có thể có hoặc không có tham số.
  * **Toán tử lambda `->`**: Phân tách danh sách tham số và thân của lambda.
  * **Thân lambda**: Có thể là một biểu thức đơn hoặc một khối lệnh (block of code).
*   **Ví dụ đơn giản:**

    ```java
    javaSao chépChỉnh sửa// Lambda không tham số
    () -> System.out.println("Hello, Lambda!");

    // Lambda có tham số
    (int a, int b) -> a + b;
    ```
* Nếu thân lambda chỉ có một biểu thức, bạn có thể không cần dấu ngoặc nhọn `{}` và không cần lệnh `return` (nếu kiểu trả về có thể suy ra).

## **3. Ứng dụng của lambda:**

*   **Functional Interfaces:** Lambda thường được sử dụng để cài đặt các functional interface, ví dụ như `Runnable`, `Comparator`, `ActionListener`, v.v.

    ```java
    javaSao chépChỉnh sửa// Ví dụ sử dụng lambda với interface Runnable:
    Runnable task = () -> System.out.println("Task is running!");
    new Thread(task).start();
    ```
*   **Collections Framework:** Lambda giúp đơn giản hóa việc xử lý các tập hợp, chẳng hạn như sử dụng phương thức `forEach`, `filter`, `map` với các stream.

    ```java
    javaSao chépChỉnh sửaList<String> names = Arrays.asList("Alice", "Bob", "Charlie");
    names.forEach(name -> System.out.println(name));
    ```
* **Event Handling:** Trong GUI programming, lambda giúp đơn giản hóa việc cài đặt các listener.

## **4. Lợi ích của việc sử dụng lambda:**

* **Code ngắn gọn và dễ đọc:** Lambda giúp loại bỏ sự phức tạp của các lớp ẩn danh (anonymous classes) khi cài đặt các interface có một phương thức.
* **Tăng tính linh hoạt:** Cho phép truyền hành vi (behavior) dưới dạng đối tượng, dễ dàng tích hợp với lập trình hàm.
* **Sự tương thích với các API hiện đại:** Nhiều API trong Java 8 và sau này (như Stream API) được thiết kế để làm việc với lambda, giúp cho việc xử lý dữ liệu trở nên trực quan hơn.

## **5. Ví dụ thực tế:**

```java
javaSao chépChỉnh sửaimport java.util.Arrays;
import java.util.List;

public class LambdaExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
        
        // Sử dụng lambda để in từng số ra console
        numbers.forEach(number -> System.out.println(number));
        
        // Sử dụng lambda để tính tổng các số
        int sum = numbers.stream().reduce(0, (a, b) -> a + b);
        System.out.println("Tổng: " + sum);
    }
}
```

***

## Toms lai

Lambda trong Java là một biểu thức cho phép định nghĩa các hàm vô danh một cách ngắn gọn, giúp cài đặt các functional interface dễ dàng và làm cho mã nguồn trở nên rõ ràng, súc tích hơn. Đây là một trong những tính năng mạnh mẽ hỗ trợ lập trình hàm trong Java, đặc biệt hữu ích khi làm việc với các API hiện đại như Stream API.
