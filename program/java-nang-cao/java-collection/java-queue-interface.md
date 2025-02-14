# Java Queue Interface

## 1. Khái niệm

**Queue Interface** là một giao diện trong Java Collections Framework, được thiết kế để lưu trữ các phần tử theo thứ tự nhất định, thường là theo nguyên tắc **FIFO (First-In-First-Out)** – tức là phần tử được thêm vào đầu tiên sẽ là phần tử được lấy ra đầu tiên. Dưới đây là một số điểm chính về Queue Interface:

## **2. Mục đích và nguyên tắc hoạt động:**

<figure><img src="../../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* **FIFO (First-In-First-Out):** Đây là cách hoạt động mặc định của hàng đợi, đảm bảo rằng thứ tự xử lý của các phần tử là theo thứ tự chúng được thêm vào.
* **Quy trình xử lý:** Queue thường được sử dụng trong các tình huống cần quản lý các yêu cầu, tác vụ hoặc các phần tử cần xử lý theo thứ tự như hệ thống in, xử lý tác vụ, quản lý phiên làm việc, v.v.

## **3. Các phương thức chính của Queue Interface:**

* **Thêm phần tử:**
  * `add(E e)`: Thêm phần tử vào cuối hàng đợi. Nếu không thể thêm (ví dụ: hàng đợi có giới hạn và đã đầy), phương thức này sẽ ném ngoại lệ.
  * `offer(E e)`: Thêm phần tử vào cuối hàng đợi. Nếu không thể thêm, phương thức này sẽ trả về `false` thay vì ném ngoại lệ.
* **Lấy và loại bỏ phần tử:**
  * `remove()`: Lấy và loại bỏ phần tử đầu tiên của hàng đợi. Nếu hàng đợi rỗng, ném ngoại lệ.
  * `poll()`: Lấy và loại bỏ phần tử đầu tiên của hàng đợi. Nếu hàng đợi rỗng, trả về `null`.
* **Xem phần tử mà không loại bỏ:**
  * `element()`: Trả về phần tử đầu tiên của hàng đợi mà không loại bỏ nó. Nếu hàng đợi rỗng, ném ngoại lệ.
  * `peek()`: Trả về phần tử đầu tiên của hàng đợi mà không loại bỏ nó. Nếu hàng đợi rỗng, trả về `null`.

## **4. Các cài đặt phổ biến của Queue Interface:**

* **`LinkedList`:** Lớp này không chỉ là một danh sách liên kết mà còn cài đặt giao diện Queue, cho phép sử dụng các phương thức của Queue.
* **`PriorityQueue`:** Cài đặt Queue mà thứ tự của các phần tử được xác định bởi thứ tự ưu tiên (theo thứ tự tự nhiên của các phần tử hoặc theo Comparator được cung cấp), không hoàn toàn theo thứ tự chèn.
* **`ArrayDeque`:** Lớp này cung cấp một cài đặt của Deque (Double Ended Queue) có thể sử dụng như một hàng đợi (Queue) hoặc ngăn xếp (Stack).

## **5. Ứng dụng của Queue:**

* **Xử lý tác vụ:** Hàng đợi được sử dụng trong việc quản lý các tác vụ cần xử lý theo thứ tự, chẳng hạn như xử lý yêu cầu trong máy chủ web hoặc hệ thống in.
* **Mô phỏng hệ thống:** Thường được dùng để mô phỏng các hệ thống như hàng đợi khách hàng tại ngân hàng, xe bus, v.v.
* **Giao tiếp giữa các luồng (threads):** Trong lập trình đa luồng, Queue có thể được sử dụng để trao đổi thông tin giữa các luồng (producer-consumer pattern).

***

**Tóm lại:**\
Queue Interface cung cấp một cấu trúc dữ liệu hữu ích để lưu trữ và xử lý các phần tử theo thứ tự, đảm bảo rằng phần tử được thêm vào đầu tiên sẽ được xử lý đầu tiên. Các phương thức của Queue hỗ trợ việc thêm, lấy và kiểm tra phần tử một cách linh hoạt, giúp nó trở thành một công cụ quan trọng trong việc quản lý các tác vụ và yêu cầu trong nhiều ứng dụng khác nhau.
