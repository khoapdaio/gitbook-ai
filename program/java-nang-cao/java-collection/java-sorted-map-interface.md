# Java Sorted Map Interface

## 1. Khái niệm

`SortedMap` là một giao diện con của `Map` trong Java Collections Framework, cung cấp các chức năng mở rộng để lưu trữ các cặp khóa - giá trị theo thứ tự sắp xếp của **khóa**. Điều này có nghĩa là mọi khi bạn thêm một cặp mới vào một đối tượng `SortedMap`, các khóa sẽ được duy trì theo một thứ tự nhất định, đó có thể là thứ tự tự nhiên của các đối tượng (nếu các khóa implement `Comparable`) hoặc theo thứ tự được xác định bởi một `Comparator` được cung cấp.

## **2. Đặc điểm chính**

### **2.1 Sắp xếp theo khóa:**

* Các phần tử trong `SortedMap` luôn được sắp xếp dựa trên **khóa**.
* Thứ tự sắp xếp có thể là thứ tự tự nhiên (natural ordering) hoặc được xác định bởi một `Comparator` khi khởi tạo bản đồ.

### **2.2 Các phương thức đặc trưng của `SortedMap`:**

| Phương thức                      |                                                                                                                  |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **`firstKey()`**                 |  Trả về khóa đầu tiên (nhỏ nhất) trong bản đồ.                                                                   |
| **`lastKey()`**                  | Trả về khóa cuối cùng (lớn nhất) trong bản đồ.                                                                   |
| **`headMap(K toKey)`**           | Trả về một `SortedMap` chứa tất cả các phần tử có khóa nhỏ hơn `toKey`.                                          |
| **`tailMap(K fromKey)`**         | Trả về một `SortedMap` chứa tất cả các phần tử có khóa lớn hơn hoặc bằng `fromKey`.                              |
| **`subMap(K fromKey, K toKey)`** | Trả về một `SortedMap` chứa các phần tử có khóa trong khoảng từ `fromKey` (bao gồm) đến `toKey` (không bao gồm). |

### **2.3 Cài đặt phổ biến:**

**`TreeMap`** là cài đặt phổ biến nhất của `SortedMap`. Lớp này sử dụng cấu trúc cây (thường là cây đỏ-đen) để đảm bảo rằng các khóa được lưu trữ theo thứ tự đã định.

## **3. Code:**

```java
import java.util.SortedMap;
import java.util.TreeMap;

public class SortedMapExample {
    public static void main(String[] args) {
        SortedMap<Integer, String> map = new TreeMap<>();
        
        // Thêm các cặp key-value vào map
        map.put(3, "Ba");
        map.put(1, "Một");
        map.put(2, "Hai");
        map.put(5, "Năm");
        map.put(4, "Bốn");

        // In ra map: các khóa sẽ được sắp xếp tự động theo thứ tự tăng dần
        System.out.println("SortedMap: " + map);

        // Lấy khóa đầu tiên và cuối cùng
        System.out.println("First key: " + map.firstKey());
        System.out.println("Last key: " + map.lastKey());

        // Lấy một phần của map
        SortedMap<Integer, String> headMap = map.headMap(3);
        System.out.println("HeadMap (keys < 3): " + headMap);

        SortedMap<Integer, String> tailMap = map.tailMap(3);
        System.out.println("TailMap (keys >= 3): " + tailMap);

        SortedMap<Integer, String> subMap = map.subMap(2, 5);
        System.out.println("SubMap (keys từ 2 đến 4): " + subMap);
    }
}
```

## **4. Khi nào nên sử dụng `SortedMap`:**

* Khi bạn cần một cấu trúc dữ liệu lưu trữ các cặp khóa - giá trị và yêu cầu các khóa phải được duy trì theo thứ tự sắp xếp.
* Khi cần thực hiện các thao tác truy vấn theo phạm vi dựa trên thứ tự của khóa (ví dụ: lấy tất cả các phần tử có khóa nhỏ hơn một giá trị nhất định).

***

Tóm lại, **`SortedMap`** là một giao diện mở rộng của `Map`, giúp bạn lưu trữ các cặp khóa - giá trị theo thứ tự sắp xếp của khóa, đồng thời cung cấp các phương thức hữu ích để thao tác với các phần tử dựa trên thứ tự đó. Cài đặt phổ biến của nó là `TreeMap`
