# Java - Generics

## Khái niệm

Generics trong Java là một cơ chế cho phép định nghĩa các lớp, giao diện và phương thức có thể hoạt động với các kiểu dữ liệu khác nhau mà vẫn đảm bảo tính an toàn về kiểu dữ liệu (type safety tại thười điểm biên dịch). Điều này có nghĩa là bạn có thể viết code một cách tổng quát generic để tái sử dụng cho nhiều kiểu dữ liệu khác nhau mà không cần phải chuyển đổi kiểu dữ liệu thủ công (casting)

## Tại sao Generics

Generics giải quyết một số vấn đề chính trong lập trình Java

* **An toàn kiểu:** An toàn kiểu là một khía cạnh quan trọng trong lập trình Java. Trước khi có generics, các collection trong Java có thể chứa bất kỳ loại đối tượng nào, điều này có nghĩa là lỗi kiểu chỉ có thể được phát hiện khi chạy chương trình, không phải khi biên dịch. Thiếu an toàn kiểu có thể dẫn đến lỗi ClassCastException khi một
* **Loại bỏ Ép kiểu:** Generics giảm nhu cầu ép kiểu rõ ràng, làm cho mã ngắn gọn và ít lỗi hơn. Không có generics, các nhà phát triển thường phải ép kiểu đối tượng sang kiểu mong muốn, dẫn đến mã lộn xộn và có khả năng xảy ra lỗi thời gian chạy.&#x20;
* **Hỗ Trợ Mã Đọc Dễ Dàng và Bảo Trì:** Generics làm cho mã trở nên dễ đọc và bảo trì hơn bằng cách nêu rõ loại nào đang được sử dụng. Sự rõ ràng này giúp các nhà phát triển khác hiểu rõ mục đích sử dụng của các bộ sưu tập và phương thức, giảm khả năng xảy ra lỗi.&#x20;
* **Nâng Cao Khung Java Collections:** Việc giới thiệu generics đã tăng cường đáng kể Khung Java Collections, làm cho nó mạnh mẽ và an toàn hơn với loại. Các bộ sưu tập giờ đây có thể được tham số hóa với các loại cụ thể, đảm bảo an toàn loại và giảm nguy cơ lỗi thời gian chạy.&#x20;
* **Cho Phép Các Thuật Toán Tổng Quát:** Generics cho phép tạo ra các thuật toán tổng quát có thể hoạt động với bất kỳ loại nào, tăng cường khả năng linh hoạt của mã. Điều này đặc biệt hữu ích trong các bộ sưu tập và các cấu trúc dữ liệu khác.&#x20;
* **Tái Sử Dụng Mã:** Generics cho phép tạo ra mã tổng quát và tái sử dụng hơn. Bằng cách tham số hóa kiểu, chúng ta có thể viết các phương thức và lớp có thể hoạt động trên bất kỳ kiểu nào, giảm trùng lặp mã và tăng cường tính linh hoạt.
* **Tương thích ngược:** Generics trong Java được thiết kế với việc xóa kiểu (type erasure) để đảm bảo tương thích ngược với các phiên bản cũ hơn của Java. Type erasure có nghĩa là thông tin kiểu generic chỉ có sẵn tại thời điểm biên dịch và bị loại bỏ tại thời điểm chạy. Nó cho phép mã generic tương tác với mã cũ không sử dụng generics.&#x20;
* **Hỗ trợ suy luận kiểu:** Cơ chế suy luận kiểu của Java hoạt động tốt với generics, cho phép trình biên dịch suy ra các tham số kiểu trong nhiều trường hợp, điều này đơn giản hóa mã cho nhà phát triển.

## Cách sử dụng

**Generic Class:** Cho phép định nghĩa lớp với tham số kiểu.

```java
public class Box<T> {
    private T content;

    public void setContent(T content) {
        this.content = content;
    }

    public T getContent() {
        return content;
    }
}
```

Ở ví dụ trên, `T` là tham số kiểu đại diện cho bất kỳ kiểu dữ liệu nào mà bạn muốn sử dụng khi khởi tạo đối tượng `Box`.

**Generic Interface:** Tương tự như generic class, interface cũng có thể được định nghĩa với tham số kiểu.

```java
public interface Container<T> {
    void add(T element);
    T get(int index);
}
```

**Generic Method:** Bạn có thể định nghĩa phương thức với tham số kiểu riêng biệt, độc lập với lớp chứa nó.

```java
public class Utility {
    public static <E> void printArray(E[] array) {
        for (E element : array) {
            System.out.println(element);
        }
    }
}
```

Trong ví dụ trên, `<E>` khai báo một tham số kiểu cho phương thức `printArray`.

