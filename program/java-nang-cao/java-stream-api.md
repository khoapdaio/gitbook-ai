# Java - Stream API

**Streams API** trong Java là một tập hợp các lớp và giao diện được giới thiệu từ Java 8, cho phép xử lý các tập hợp dữ liệu (collections, arrays, v.v.) theo kiểu **lập trình hàm (functional programming)** và **pipeline processing**. Streams API không lưu trữ dữ liệu mà là một kênh (stream) cho phép bạn thực hiện các thao tác trên dữ liệu một cách trôi chảy và hiệu quả. Dưới đây là một số điểm chính:

## **Xử lý dữ liệu theo pipeline:**

* Streams API cho phép bạn chuyển đổi một nguồn dữ liệu (ví dụ: một `Collection` hay mảng) thành một stream. Từ đó, bạn có thể áp dụng một chuỗi các thao tác (như filter, map, sort, …) một cách liên tục, được gọi là pipeline.
* Các thao tác trên stream thường được chia thành 2 loại:
  * **Intermediate operations (thao tác trung gian):** Như `filter()`, `map()`, `sorted()`, … Các thao tác này không thực thi ngay lập tức mà tạo ra một pipeline để xử lý.
  * **Terminal operations (thao tác cuối cùng):** Như `collect()`, `forEach()`, `reduce()`, … Các thao tác này kích hoạt quá trình xử lý pipeline và trả về kết quả hoặc thực hiện tác vụ phụ.

## **Lazy Evaluation:**

* Các thao tác trung gian trong Streams API được tính theo kiểu "lười" (lazy evaluation), nghĩa là chúng không thực hiện xử lý cho đến khi có thao tác cuối cùng được gọi. Điều này giúp tối ưu hóa hiệu năng bằng cách loại bỏ những phép tính không cần thiết.

## **Xử lý dữ liệu song song:**

* Streams API hỗ trợ xử lý dữ liệu song song (parallel processing) một cách dễ dàng. Bạn có thể chuyển đổi một stream thành song song bằng cách gọi `parallelStream()` trên Collection hoặc `parallel()` trên stream. Điều này giúp tận dụng tối đa sức mạnh của các bộ xử lý đa nhân trong việc xử lý dữ liệu lớn.

## **Lợi ích của Streams API:**

* **Code ngắn gọn và rõ ràng:** Thay vì sử dụng các vòng lặp truyền thống, bạn có thể xử lý dữ liệu theo một chuỗi các phép biến đổi dễ hiểu.
* **Tính bất biến (immutability):** Streams khuyến khích việc sử dụng các thao tác không thay đổi dữ liệu gốc, giúp tránh các lỗi không mong muốn.
* **Hiệu năng:** Nhờ lazy evaluation và khả năng xử lý song song, Streams API có thể cải thiện hiệu suất khi xử lý khối lượng dữ liệu lớn.

## **Ví dụ minh họa:**

```java
javaSao chépChỉnh sửaimport java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StreamsExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie", "David", "Anna");

        // Sử dụng Stream để lọc các tên bắt đầu bằng chữ 'A' và chuyển đổi về chữ in hoa
        List<String> filteredNames = names.stream()      // Tạo stream từ danh sách
                                           .filter(name -> name.startsWith("A")) // Lọc các tên bắt đầu bằng A
                                           .map(String::toUpperCase) // Chuyển tên thành chữ in hoa
                                           .sorted() // Sắp xếp các tên theo thứ tự tự nhiên
                                           .collect(Collectors.toList()); // Thu thập kết quả thành List

        System.out.println("Filtered Names: " + filteredNames);
    }
}
```

Trong ví dụ trên:

* **`stream()`**: Chuyển danh sách `names` thành một stream.
* **`filter(...)`**: Lọc ra các phần tử thỏa mãn điều kiện (bắt đầu bằng chữ "A").
* **`map(...)`**: Biến đổi các phần tử (chuyển thành chữ in hoa).
* **`sorted()`**: Sắp xếp các phần tử theo thứ tự tự nhiên.
* **`collect(...)`**: Thu thập kết quả cuối cùng thành một danh sách mới.

***

## **Tóm lại:**

Streams API trong Java là một công cụ mạnh mẽ cho phép xử lý các tập hợp dữ liệu theo phong cách lập trình hàm và pipeline, giúp code trở nên ngắn gọn, rõ ràng, và dễ dàng tận dụng khả năng xử lý song song để cải thiện hiệu năng. Đây là một trong những tính năng quan trọng được giới thiệu từ Java 8, giúp thay đổi cách lập trình và xử lý dữ liệu trong các ứng dụng Java hiện đại.
