# Java Set Interface

## 1. Khái niệm

**Set Interface** là một giao diện (interface) trong **Java Collections Framework**, nằm trong gói **java.util**. Nó đại diện cho một tập hợp các phần tử (elements) **không có thứ tự** (unordered) và **không cho phép trùng lặp** (no duplicates). Set Interface kế thừa từ **Collection Interface** và mở rộng thêm các tính năng đặc thù cho tập hợp.

***

## **2. Đặc điểm chính của Set Interface**

1. **Không cho phép trùng lặp (No Duplicates)**:
   * Mỗi phần tử trong Set là duy nhất. Nếu bạn cố gắng thêm một phần tử đã tồn tại, nó sẽ không được thêm vào.
2. **Không có thứ tự (Unordered)**:
   * Các phần tử trong Set không được sắp xếp theo bất kỳ thứ tự cụ thể nào (trừ một số triển khai như `LinkedHashSet` hoặc `TreeSet`).
3. **Cho phép phần tử null**:
   * Set có thể chứa một phần tử `null` (trừ `TreeSet`, không cho phép `null`).
4. **Không có chỉ số (No Index)**:
   * Bạn không thể truy cập các phần tử trong Set bằng chỉ số (index).

***

## **3. Các phương thức chính của Set Interface**

Set Interface kế thừa tất cả các phương thức từ **Collection Interface**, bao gồm:

| Phương thức          | Mô tả                                                   |
| -------------------- | ------------------------------------------------------- |
| `add(E e)`           | Thêm một phần tử vào Set (nếu phần tử chưa tồn tại).    |
| `remove(Object o)`   | Xóa một phần tử khỏi Set.                               |
| `contains(Object o)` | Kiểm tra xem Set có chứa phần tử được chỉ định không.   |
| `size()`             | Trả về số lượng phần tử trong Set.                      |
| `isEmpty()`          | Kiểm tra xem Set có rỗng không.                         |
| `clear()`            | Xóa tất cả các phần tử khỏi Set.                        |
| `iterator()`         | Trả về một iterator để duyệt qua các phần tử trong Set. |
| `toArray()`          | Chuyển đổi Set thành một mảng.                          |

***

## **4. Các lớp triển khai Set Interface**

Có nhiều lớp triển khai (implement) Set Interface trong Java, phổ biến nhất là:

1. **HashSet**:
   * Sử dụng bảng băm (hash table) để lưu trữ các phần tử.
   * Không đảm bảo thứ tự các phần tử.
   * Hiệu suất tốt nhất trong hầu hết các trường hợp.
2. **LinkedHashSet**:
   * Kế thừa từ `HashSet`, nhưng duy trì thứ tự chèn (insertion order) của các phần tử.
   * Hiệu suất thấp hơn `HashSet` một chút.
3. **TreeSet**:
   * Sử dụng cây (tree) để lưu trữ các phần tử.
   * Các phần tử được sắp xếp theo thứ tự tăng dần (theo thứ tự tự nhiên hoặc bộ so sánh - Comparator).
   * Không cho phép phần tử `null`.

***

## 5. Code

```java
import java.util.HashSet;
import java.util.Set;

public class SetExample {
    public static void main(String[] args) {
        // Tạo một HashSet
        Set<String> fruits = new HashSet<>();

        // Thêm phần tử vào Set
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Apple"); // Phần tử trùng lặp, sẽ không được thêm vào

        // In Set
        System.out.println("Fruits: " + fruits);

        // Kiểm tra kích thước Set
        System.out.println("Size of Set: " + fruits.size());

        // Kiểm tra xem Set có chứa phần tử không
        System.out.println("Contains Banana? " + fruits.contains("Banana"));

        // Xóa phần tử
        fruits.remove("Orange");
        System.out.println("After removing Orange: " + fruits);

        // Duyệt qua Set
        for (String fruit : fruits) {
            System.out.println(fruit);
        }

        // Xóa tất cả phần tử
        fruits.clear();
        System.out.println("After clearing: " + fruits);
    }
}
```

***

## **6. So sánh các lớp triển khai Set**

<table data-header-hidden data-full-width="true"><thead><tr><th></th><th></th><th></th><th></th><th></th></tr></thead><tbody><tr><td>Lớp triển khai</td><td>Thứ tự phần tử</td><td>Cho phép <code>null</code></td><td>Hiệu suất</td><td>Sử dụng khi nào?</td></tr><tr><td><strong>HashSet</strong></td><td>Không có thứ tự</td><td>Có</td><td>O(1) cho các thao tác cơ bản</td><td>Cần hiệu suất cao, không quan tâm thứ tự.</td></tr><tr><td><strong>LinkedHashSet</strong></td><td>Thứ tự chèn</td><td>Có</td><td>Chậm hơn <code>HashSet</code> một chút</td><td>Cần duy trì thứ tự chèn.</td></tr><tr><td><strong>TreeSet</strong></td><td>Thứ tự tăng dần</td><td>Không</td><td>O(log n) cho các thao tác cơ bản</td><td>Cần các phần tử được sắp xếp.</td></tr></tbody></table>

***

## **7. Kết luận**

Set Interface là một công cụ mạnh mẽ để làm việc với các tập hợp không trùng lặp trong Java. Tùy vào nhu cầu cụ thể, bạn có thể chọn các lớp triển khai như `HashSet`, `LinkedHashSet`, hoặc `TreeSet` để đạt được hiệu suất và tính năng phù hợp.
