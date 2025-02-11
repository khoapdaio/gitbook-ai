# Java Map Interface

## 1. Khái niệm

**Map Interface** là một giao diện trong Java Collections Framework được sử dụng để lưu trữ các cặp khóa - giá trị (key-value pairs). Nó không mở rộng từ giao diện `Collection` mà có cấu trúc và phương thức riêng để thao tác với các cặp dữ liệu.

## **2. Cấu trúc dữ liệu:**

* **Cặp key-value:** Mỗi phần tử trong Map là một cặp gồm một khóa (`key`) và một giá trị (`value`). Mỗi khóa là duy nhất và ánh xạ đến một giá trị tương ứng.
* **Không cho phép trùng lặp khóa:** Nếu bạn cố gắng thêm một cặp mới với một khóa đã tồn tại, giá trị cũ sẽ bị ghi đè bởi giá trị mới.

## **3. Các phương thức chính:**

|                               |                                                                                           |
| ----------------------------- | ----------------------------------------------------------------------------------------- |
| `put(K key, V value)`         |  Thêm hoặc cập nhật một cặp key-value vào Map.                                            |
| `get(Object key)`             | Lấy giá trị tương ứng với khóa được cung cấp.                                             |
| `remove(Object key)`          | Xóa cặp key-value tương ứng với khóa.                                                     |
| `containsKey(Object key)`     | Kiểm tra xem Map có chứa khóa đó hay không.                                               |
| `containsValue(Object value)` | Kiểm tra xem Map có chứa giá trị đó hay không.                                            |
| `keySet()`                    | Trả về một tập hợp (`Set`) các khóa có trong Map.                                         |
| `values()`                    | Trả về một tập hợp (`Collection`) các giá trị có trong Map.                               |
| `entrySet()`                  | Trả về một tập hợp các phần tử kiểu `Map.Entry<K,V>`, mỗi phần tử chứa một cặp key-value. |

## **4. Các cài đặt phổ biến của Map Interface:**

* **`HashMap`:** Lưu trữ các phần tử theo bảng băm, không đảm bảo thứ tự của các phần tử.
* **`TreeMap`:** Lưu trữ các phần tử theo cấu trúc cây (thường là cây đỏ-đen), đảm bảo thứ tự tự nhiên của các khóa hoặc theo thứ tự do `Comparator` cung cấp.
* **`LinkedHashMap`:** Giữ thứ tự chèn (insertion order) hoặc thứ tự truy cập (access order) của các phần tử, đồng thời hoạt động như một bảng băm.
* **`Hashtable`:** Tương tự như `HashMap` nhưng được đồng bộ hóa (thread-safe) và không cho phép giá trị null.

## **5. Code**

```java
import java.util.HashMap;
import java.util.Map;

public class MapExample {
    public static void main(String[] args) {
        // Khởi tạo một HashMap
        Map<String, Integer> studentGrades = new HashMap<>();

        // Thêm các cặp key-value vào Map
        studentGrades.put("Alice", 85);
        studentGrades.put("Bob", 90);
        studentGrades.put("Charlie", 78);
        // Nếu thêm "Bob" một lần nữa, giá trị sẽ được cập nhật
        studentGrades.put("Bob", 95);

        // Lấy giá trị dựa trên khóa
        System.out.println("Điểm của Bob: " + studentGrades.get("Bob"));

        // Kiểm tra sự tồn tại của một khóa
        if (studentGrades.containsKey("Alice")) {
            System.out.println("Alice có trong danh sách.");
        }

        // Duyệt qua Map bằng cách sử dụng entrySet()
        for (Map.Entry<String, Integer> entry : studentGrades.entrySet()) {
            System.out.println("Tên: " + entry.getKey() + ", Điểm: " + entry.getValue());
        }
    }
}
```

## **6. Khi nào nên sử dụng Map:**

* Khi bạn cần lưu trữ dữ liệu dưới dạng cặp key-value và truy xuất giá trị một cách nhanh chóng thông qua khóa.
* Khi thứ tự của các phần tử không phải là ưu tiên chính (trường hợp sử dụng `HashMap`) hoặc khi bạn cần duy trì thứ tự sắp xếp của các khóa (sử dụng `TreeMap` hoặc `LinkedHashMap`).
