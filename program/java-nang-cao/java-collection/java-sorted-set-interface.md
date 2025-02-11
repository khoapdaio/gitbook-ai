# Java Sorted Set Interface

## 1. Khái niệm&#x20;

`SortedSet` là một giao diện trong Java Collections Framework, mở rộng từ giao diện `Set`. Nó đảm bảo rằng các phần tử bên trong tập hợp được **sắp xếp theo một thứ tự nhất định** (theo thứ tự tự nhiên của các phần tử hoặc theo thứ tự do một `Comparator` cung cấp). Dưới đây là một số điểm chính về

## 2. Đặc điểm chính

* **Sắp xếp tự động:**\
  Các phần tử được lưu trữ trong `SortedSet` luôn được sắp xếp. Điều này có nghĩa là khi bạn thêm các phần tử mới, chúng sẽ được chèn vào vị trí thích hợp để duy trì thứ tự đã định.
* **Không chứa phần tử trùng lặp:**\
  Tương tự như các giao diện `Set` khác, `SortedSet` không cho phép chứa các phần tử trùng lặp.
* **Yêu cầu tính so sánh của các phần tử:**
  * Các phần tử trong `SortedSet` phải **implement giao diện `Comparable`** để có thể so sánh lẫn nhau theo thứ tự tự nhiên.
  * Hoặc bạn có thể cung cấp một `Comparator` khi khởi tạo tập hợp để xác định thứ tự sắp xếp theo ý muốn.

## 3. Các phương thức đặc trưng:

| Phương thức                          | Mô tả                                                                                                                 |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| `first()`                            | Trả về phần tử nhỏ nhất trong tập hợp                                                                                 |
| `last()`                             | Trả về phần tử lớn nhất trong tập hợp.                                                                                |
| `headSet(E toElement)`               | Trả về một `SortedSet` chứa tất cả các phần tử nhỏ hơn `toElement`.                                                   |
| `tailSet(E fromElement)`             | Trả về một `SortedSet` chứa tất cả các phần tử lớn hơn hoặc bằng `fromElement`.                                       |
| `subSet(E fromElement, E toElement)` |  Trả về một `SortedSet` chứa các phần tử nằm trong khoảng từ `fromElement` (bao gồm) đến `toElement` (không bao gồm). |

## 4. Code

```java
import java.util.SortedSet;
import java.util.TreeSet;

public class SortedSetExample {
    public static void main(String[] args) {
        SortedSet<Integer> numbers = new TreeSet<>();
        numbers.add(20);
        numbers.add(5);
        numbers.add(15);
        numbers.add(10);
        
        // In ra tập hợp, kết quả sẽ được sắp xếp tự động: [5, 10, 15, 20]
        System.out.println("SortedSet: " + numbers);
        
        // Lấy phần tử nhỏ nhất và lớn nhất
        System.out.println("First element: " + numbers.first());
        System.out.println("Last element: " + numbers.last());
        
        // Lấy tập hợp con chứa các phần tử nhỏ hơn 15
        SortedSet<Integer> headSet = numbers.headSet(15);
        System.out.println("HeadSet (elements < 15): " + headSet);
        
        // Lấy tập hợp con chứa các phần tử từ 10 trở đi
        SortedSet<Integer> tailSet = numbers.tailSet(10);
        System.out.println("TailSet (elements >= 10): " + tailSet);
    }
}

```

