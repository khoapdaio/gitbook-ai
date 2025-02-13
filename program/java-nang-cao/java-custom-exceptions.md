# Java - Custom Exceptions

## 1. Định nghĩa

**Custom Exceptions** (Ngoại lệ tùy chỉnh) trong Java là những lớp ngoại lệ do lập trình viên tự định nghĩa nhằm xử lý các tình huống lỗi đặc thù mà các ngoại lệ có sẵn trong Java không thể mô tả đầy đủ. Việc tạo custom exceptions giúp:

* **Tăng tính rõ ràng của mã nguồn:**\
  Khi bạn định nghĩa một ngoại lệ tùy chỉnh, tên của nó sẽ mô tả rõ ràng nguyên nhân lỗi, giúp code trở nên dễ hiểu và dễ bảo trì hơn.
* **Xử lý lỗi theo cách riêng:**\
  Bạn có thể thêm các thông tin bổ sung hoặc logic xử lý đặc biệt cho từng loại lỗi cụ thể trong ứng dụng của mình.
* **Phân biệt lỗi nghiệp vụ:**\
  Custom exceptions cho phép bạn phân biệt các lỗi liên quan đến nghiệp vụ ứng dụng so với các lỗi hệ thống, từ đó dễ dàng quản lý và xử lý.

## 2. Cách tạo Custom Exception

Để tạo một custom exception, bạn thường làm theo một trong hai cách:

1.  **Kế thừa từ `Exception`:**\
    Dùng để tạo ra **checked exceptions** (ngoại lệ được kiểm tra khi biên dịch), yêu cầu bắt hoặc khai báo ném ra ngoại lệ đó.

    ```java
    public class InvalidAgeException extends Exception {
        public InvalidAgeException(String message) {
            super(message);
        }
    }
    ```
2.  **Kế thừa từ `RuntimeException`:**\
    Dùng để tạo ra **unchecked exceptions** (ngoại lệ không kiểm tra khi biên dịch), thường được sử dụng cho các lỗi lập trình.

    ```java
    public class NegativeBalanceException extends RuntimeException {
        public NegativeBalanceException(String message) {
            super(message);
        }
    }
    ```

## 3. Ví dụ sử dụng Custom Exception

Giả sử bạn có một lớp `Person` với thuộc tính `age`, và bạn muốn đảm bảo rằng tuổi không được âm:

```java
public class Person {
    private int age;

    public void setAge(int age) throws InvalidAgeException {
        if(age < 0) {
            throw new InvalidAgeException("Tuổi không hợp lệ: " + age);
        }
        this.age = age;
    }

    public static void main(String[] args) {
        Person person = new Person();
        try {
            person.setAge(-5);
        } catch (InvalidAgeException e) {
            System.out.println("Lỗi: " + e.getMessage());
        }
    }
}
```

Trong ví dụ trên:

* Lớp `InvalidAgeException` được tạo ra để xử lý lỗi liên quan đến tuổi không hợp lệ.
* Phương thức `setAge` kiểm tra giá trị tuổi và ném `InvalidAgeException` nếu tuổi âm.
* Khối `try-catch` trong `main` xử lý ngoại lệ này một cách có kiểm soát.
