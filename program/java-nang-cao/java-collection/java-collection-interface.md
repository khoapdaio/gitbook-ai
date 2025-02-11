# Java Collection Interface

## 1. Khái niệm

**Collection Interface** là một giao diện (interface) cốt lõi trong **Java Collections Framework (JCF)**, nằm trong gói **java.util**. Nó đại diện cho một nhóm các đối tượng (objects) được gọi là các phần tử (elements). Collection Interface là nền tảng cho tất cả các cấu trúc dữ liệu tập hợp trong Java, bao gồm List, Set, Queue, và các cấu trúc dữ liệu khác.

## 2. Vai trò

* Định nghĩa các phương thức cơ bản để thao tác với một nhóm các đối tượng.
* Cung cấp một cách thống nhất để làm việc với các cấu trúc dữ liệu khác nhau như List, Set, Queue.
* Cho phép các lớp triển khai (implement) tự định nghĩa cách lưu trữ và quản lý các phần tử.

## **3. Các phương thức chính của Collection Interface**

Dưới đây là các phương thức phổ biến của Collection Interface:

| Phương thức                         | Mô tả                                                                         |
| ----------------------------------- | ----------------------------------------------------------------------------- |
| `add(E e)`                          | Thêm một phần tử vào collection.                                              |
| `addAll(Collection<? extends E> c)` | Thêm tất cả các phần tử từ một collection khác vào collection hiện tại.       |
| `remove(Object o)`                  | Xóa một phần tử khỏi collection.                                              |
| `removeAll(Collection<?> c)`        | Xóa tất cả các phần tử thuộc collection được chỉ định.                        |
| `retainAll(Collection<?> c)`        | Giữ lại chỉ các phần tử thuộc collection được chỉ định.                       |
| `clear()`                           | Xóa tất cả các phần tử khỏi collection.                                       |
| `size()`                            | Trả về số lượng phần tử trong collection.                                     |
| `isEmpty()`                         | Kiểm tra xem collection có rỗng không.                                        |
| `contains(Object o)`                | Kiểm tra xem collection có chứa phần tử được chỉ định không.                  |
| `containsAll(Collection<?> c)`      | Kiểm tra xem collection có chứa tất cả các phần tử của collection khác không. |
| `iterator()`                        | Trả về một iterator để duyệt qua các phần tử trong collection.                |
| `toArray()`                         | Chuyển đổi collection thành một mảng.                                         |
| `toArray(T[] a)`                    | Chuyển đổi collection thành một mảng với kiểu dữ liệu được chỉ định.          |

## 4. Code

```java
import java.util.ArrayList;
import java.util.Collection;

public class CollectionExample {
    public static void main(String[] args) {
        // Tạo một collection (sử dụng ArrayList)
        Collection<String> fruits = new ArrayList<>();

        // Thêm phần tử vào collection
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");

        // In collection
        System.out.println("Fruits: " + fruits);

        // Kiểm tra kích thước collection
        System.out.println("Size of collection: " + fruits.size());

        // Kiểm tra xem collection có chứa phần tử không
        System.out.println("Contains Apple? " + fruits.contains("Apple"));

        // Xóa phần tử
        fruits.remove("Banana");
        System.out.println("After removing Banana: " + fruits);

        // Duyệt qua collection
        for (String fruit : fruits) {
            System.out.println(fruit);
        }

        // Xóa tất cả phần tử
        fruits.clear();
        System.out.println("After clearing: " + fruits);
    }
}
```



