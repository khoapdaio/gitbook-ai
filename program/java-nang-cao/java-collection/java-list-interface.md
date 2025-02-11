# Java List Interface

## 1 Khái niệm&#x20;

List là một giao diện interface trong Java Collection Framework, đại diện cho một danh sách các phần tử có thứ tự (ordered) và cho phép chứa các phần tử trùng lặp. List là một trong những cấu trúc dữ liệu được sử dụng phổ biến trong Java, cung cấp nhiều phương thức để thao tác với các phần tử trong danh sách

## **2 Đặc điểm chính của List**

1. **Thứ tự (Ordered)**:
   * Các phần tử trong List được lưu trữ theo một thứ tự cụ thể (theo chỉ số).
   * Bạn có thể truy cập các phần tử bằng chỉ số (index).
2. **Cho phép trùng lặp (Allows Duplicates)**:
   * List có thể chứa nhiều phần tử giống nhau.
3. **Cho phép phần tử null**:
   * List có thể chứa các phần tử `null`.
4. **Có thể thay đổi kích thước (Dynamic Size)**:
   * List có thể tự động mở rộng hoặc thu nhỏ kích thước khi thêm hoặc xóa phần tử.

## **3 Các phương thức chính của List**

**Dưới đây là một số phương thức phổ biến của List:**

| Phương thức                 | Mô tả                                                                 |
| --------------------------- | --------------------------------------------------------------------- |
| `add(E e)`                  | Thêm một phần tử vào cuối danh sách.                                  |
| `add(int index, E element)` | Thêm một phần tử vào vị trí chỉ định.                                 |
| `get(int index)`            | Lấy phần tử tại vị trí chỉ định.                                      |
| `remove(int index)`         | Xóa phần tử tại vị trí chỉ định.                                      |
| `remove(Object o)`          | Xóa phần tử đầu tiên bằng với đối tượng được chỉ định.                |
| `set(int index, E element)` | Thay thế phần tử tại vị trí chỉ định bằng phần tử mới.                |
| `size()`                    | Trả về số lượng phần tử trong danh sách.                              |
| `isEmpty()`                 | Kiểm tra xem danh sách có rỗng không.                                 |
| `contains(Object o)`        | Kiểm tra xem danh sách có chứa phần tử được chỉ định không.           |
| `indexOf(Object o)`         | Trả về chỉ số của phần tử đầu tiên bằng với đối tượng được chỉ định.  |
| `lastIndexOf(Object o)`     | Trả về chỉ số của phần tử cuối cùng bằng với đối tượng được chỉ định. |
| `clear()`                   | Xóa tất cả các phần tử trong danh sách.                               |
| `iterator()`                | Trả về một iterator để duyệt qua các phần tử trong danh sách.         |

## 4. Code

```java
import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        // Tạo một ArrayList
        List<String> fruits = new ArrayList<>();

        // Thêm phần tử vào danh sách
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");

        // In danh sách
        System.out.println("Fruits: " + fruits);

        // Truy cập phần tử bằng chỉ số
        System.out.println("First fruit: " + fruits.get(0));

        // Thêm phần tử vào vị trí chỉ định
        fruits.add(1, "Mango");
        System.out.println("After adding Mango: " + fruits);

        // Xóa phần tử
        fruits.remove("Banana");
        System.out.println("After removing Banana: " + fruits);

        // Kiểm tra kích thước danh sách
        System.out.println("Size of list: " + fruits.size());

        // Kiểm tra xem danh sách có chứa phần tử không
        System.out.println("Contains Apple? " + fruits.contains("Apple"));

        // Duyệt qua danh sách
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```



