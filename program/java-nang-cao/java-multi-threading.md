# Java - Multi Threading

## 1. Phân biệt Thread và Process

* **Process (Tiến trình):**
  * Là đơn vị thực thi độc lập của một chương trình.
  * Mỗi process có không gian bộ nhớ riêng và các tài nguyên riêng biệt.
  * Các process khác nhau không chia sẻ bộ nhớ, do đó giao tiếp giữa các process (Inter-process Communication - IPC) phức tạp hơn.
  * Ví dụ: Một trình duyệt, một trình soạn thảo văn bản là các process riêng biệt.
*   **Thread (Luồng):**

    * Là đơn vị thực thi nhỏ nhất bên trong một process.
    * Các thread trong cùng một process chia sẻ không gian bộ nhớ và tài nguyên của process đó.
    * Giao tiếp giữa các thread dễ dàng hơn vì cùng chung bộ nhớ, nhưng cũng dễ gặp phải các vấn đề như race condition nếu không đồng bộ hóa.
    * Ví dụ: Trong một trình duyệt, mỗi tab có thể được xử lý bởi các thread khác nhau để tải dữ liệu song song.

    <figure><img src="../../.gitbook/assets/image (1).png" alt="" width="375"><figcaption><p><a href="https://www.scaler.com/topics/thread-in-java/">https://www.scaler.com/topics/thread-in-java/</a></p></figcaption></figure>

***

## 2. Vòng đời của Thread

Thread trong Java có các trạng thái chính như sau:

1. **New (Mới tạo):**
   * Thread được tạo ra (new Thread(...)) nhưng chưa được gọi `start()`.
2. **Runnable (Sẵn sàng chạy):**
   * Sau khi gọi `start()`, thread chuyển sang trạng thái runnable. Ở trạng thái này, thread sẵn sàng chạy và đang chờ CPU cấp phát thời gian thực thi.
3. **Running (Đang chạy):**
   * Khi CPU cấp phát thời gian, thread thực sự chạy phương thức `run()`.
4. **Blocked/Waiting/Timed Waiting (Chờ):**
   * **Blocked:** Khi thread bị chặn vì đang chờ truy cập tài nguyên đã bị khóa (synchronized).
   * **Waiting:** Khi thread gọi `wait()` và chờ tín hiệu từ `notify()` hoặc `notifyAll()`.
   * **Timed Waiting:** Khi thread gọi `sleep()`, `wait(timeout)` hay `join(timeout)` và chờ trong khoảng thời gian quy định.
5. **Terminated (Kết thúc):**
   * Khi phương thức `run()` hoàn tất hoặc thread bị dừng, nó chuyển sang trạng thái terminated.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

***

## 3. Tạo một Thread

Có hai cách phổ biến để tạo thread:

#### Cách 1: Mở rộng lớp `Thread`

```java
public class MyThread extends Thread {
    @Override
    public void run() {
        System.out.println("Thread đang chạy: " + Thread.currentThread().getName());
    }

    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start(); // Gọi start() sẽ chuyển thread từ trạng thái New sang Runnable
    }
}
```

#### Cách 2: Triển khai interface `Runnable`

```java
public class MyRunnable implements Runnable {
    @Override
    public void run() {
        System.out.println("Thread đang chạy: " + Thread.currentThread().getName());
    }

    public static void main(String[] args) {
        Thread thread = new Thread(new MyRunnable());
        thread.start();
    }
}
```

***

## 4. Các khái niệm quan trọng trong Thread

### 4.1. Synchronization (Đồng bộ hóa)

* **Mục đích:** Đảm bảo rằng nhiều thread không truy cập và thay đổi tài nguyên chung cùng lúc gây ra lỗi.
* **Cách sử dụng:** Dùng từ khóa `synchronized` để khóa một khối mã hoặc phương thức.

**Ví dụ:**

```java
public class Counter {
    private int count = 0;

    // Phương thức synchronized đảm bảo rằng chỉ một thread được truy cập tại một thời điểm
    public synchronized void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}

public class SyncExample {
    public static void main(String[] args) throws InterruptedException {
        Counter counter = new Counter();

        // Tạo 2 thread cùng tăng giá trị count
        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });
        Thread t2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });

        t1.start();
        t2.start();
        t1.join();
        t2.join();

        System.out.println("Count = " + counter.getCount());
    }
}
```

### 4.2. Pools (Hồ chứa Thread – Thread Pool)

* **Mục đích:** Quản lý số lượng thread hạn chế để tránh việc tạo và hủy thread nhiều lần, cải thiện hiệu suất.
* **Cách sử dụng:** Dùng `ExecutorService` từ thư viện `java.util.concurrent`.

**Ví dụ:**

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class ThreadPoolExample {
    public static void main(String[] args) {
        // Tạo một pool với 3 thread
        ExecutorService executor = Executors.newFixedThreadPool(3);

        // Gửi 5 tác vụ cho thread pool
        for (int i = 0; i < 5; i++) {
            int taskNumber = i;
            executor.submit(() -> {
                System.out.println("Task " + taskNumber + " được thực hiện bởi " + Thread.currentThread().getName());
            });
        }

        executor.shutdown(); // Đóng pool sau khi hoàn thành công việc
    }
}
```

### 4.3. Priorities (Độ ưu tiên của Thread)

* **Mục đích:** Cho phép đặt độ ưu tiên cho các thread để scheduler có thể ưu tiên chạy các thread quan trọng hơn.
* **Cách sử dụng:** Dùng `setPriority(int priority)` với giá trị từ 1 (MIN\_PRIORITY) đến 10 (MAX\_PRIORITY).

**Ví dụ:**

```java
public class PriorityExample {
    public static void main(String[] args) {
        Thread highPriority = new Thread(() -> {
            System.out.println("High Priority Thread đang chạy");
        });
        highPriority.setPriority(Thread.MAX_PRIORITY);

        Thread lowPriority = new Thread(() -> {
            System.out.println("Low Priority Thread đang chạy");
        });
        lowPriority.setPriority(Thread.MIN_PRIORITY);

        highPriority.start();
        lowPriority.start();
    }
}
```

### 4.4. Communication (Giao tiếp giữa các thread)

* **Mục đích:** Cho phép các thread giao tiếp với nhau, đặc biệt trong trường hợp cần đồng bộ hóa hoặc trao đổi dữ liệu.
* **Cách sử dụng:** Dùng các phương thức `wait()`, `notify()` và `notifyAll()` trong khối synchronized.

**Ví dụ:**

```java
public class ThreadCommunication {
    private static final Object lock = new Object();

    public static void main(String[] args) {
        Thread producer = new Thread(() -> {
            synchronized (lock) {
                System.out.println("Producer: Sẵn sàng sản xuất, thông báo cho consumer");
                lock.notify(); // Thông báo cho thread đang chờ
            }
        });

        Thread consumer = new Thread(() -> {
            synchronized (lock) {
                try {
                    System.out.println("Consumer: Đang chờ sản phẩm");
                    lock.wait(); // Chờ thông báo từ producer
                    System.out.println("Consumer: Nhận thông báo, tiếp tục xử lý");
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });

        consumer.start();
        // Để đảm bảo consumer chờ trước khi producer thông báo
        try { Thread.sleep(100); } catch (InterruptedException e) { }
        producer.start();
    }
}
```

### 4.5. Daemon (Thread nền)

* **Mục đích:** Daemon thread là các thread chạy nền, giúp hỗ trợ các thread chính. Khi tất cả các thread không phải daemon kết thúc, JVM sẽ kết thúc ngay cả khi daemon thread vẫn đang chạy.
* **Cách sử dụng:** Dùng `setDaemon(true)` trước khi gọi `start()`.

**Ví dụ:**

```java
public class DaemonExample {
    public static void main(String[] args) {
        Thread daemonThread = new Thread(() -> {
            while (true) {
                System.out.println("Daemon thread đang chạy...");
                try {
                    Thread.sleep(500);
                } catch (InterruptedException e) {
                    break;
                }
            }
        });
        daemonThread.setDaemon(true);
        daemonThread.start();

        // Thread chính ngủ 2 giây rồi kết thúc
        try { Thread.sleep(2000); } catch (InterruptedException e) { }
        System.out.println("Thread chính kết thúc");
    }
}
```

### 4.6. Safety (An toàn về thread – Thread Safety)

* **Mục đích:** Đảm bảo rằng dữ liệu chia sẻ giữa các thread không bị lỗi do các thao tác đồng thời.
* **Cách tiếp cận:** Sử dụng đồng bộ hóa (synchronized), lớp bất biến (immutable) hoặc các cấu trúc từ `java.util.concurrent` như `ConcurrentHashMap`.
* **Ví dụ:** Đã được minh họa trong phần **Synchronization** ở trên.

### 4.7. Interruption (Ngắt thread)

* **Mục đích:** Cho phép một thread báo hiệu với thread khác rằng nó nên dừng công việc hiện tại.
* **Cách sử dụng:** Dùng `interrupt()` để gửi tín hiệu ngắt, và trong thread nhận tín hiệu, kiểm tra trạng thái interruption bằng `Thread.interrupted()` hoặc xử lý `InterruptedException`.

**Ví dụ:**

```java
public class InterruptionExample {
    public static void main(String[] args) {
        Thread longTask = new Thread(() -> {
            try {
                for (int i = 0; i < 10; i++) {
                    // Giả lập công việc nặng
                    System.out.println("Đang xử lý tác vụ " + i);
                    Thread.sleep(1000);
                }
            } catch (InterruptedException e) {
                System.out.println("Thread bị ngắt giữa chừng!");
            }
        });

        longTask.start();

        // Sau 3 giây, ngắt thread
        try { Thread.sleep(3000); } catch (InterruptedException e) { }
        longTask.interrupt();
    }
}
```

### 4.8. Local Variables (Biến cục bộ của Thread – ThreadLocal)

* **Mục đích:** Cho phép mỗi thread có biến riêng biệt, không bị chia sẻ giữa các thread, giúp tránh các vấn đề về đồng bộ.
* **Cách sử dụng:** Dùng lớp `ThreadLocal<T>` để khai báo biến cục bộ cho mỗi thread.

**Ví dụ:**

```java
public class ThreadLocalExample {
    // Mỗi thread có giá trị riêng của biến threadLocal
    private static ThreadLocal<Integer> threadLocal = ThreadLocal.withInitial(() -> 0);

    public static void main(String[] args) {
        Runnable task = () -> {
            int value = threadLocal.get();
            value += 5;
            threadLocal.set(value);
            System.out.println(Thread.currentThread().getName() + " có giá trị: " + threadLocal.get());
        };

        Thread t1 = new Thread(task, "Thread-1");
        Thread t2 = new Thread(task, "Thread-2");

        t1.start();
        t2.start();
    }
}
```

***

## 5. Lỗi phổ biến&#x20;

### **5.1 Race Condition (Điều kiện cạnh tranh):**

* **Mô tả:** Nhiều thread cùng truy cập và thay đổi một tài nguyên chung (ví dụ: biến, danh sách, file,…) mà không có cơ chế đồng bộ hóa hợp lý.
* **Hậu quả:** Dữ liệu bị thay đổi không nhất quán, dẫn đến kết quả không dự đoán được.
* **Giải pháp:** Sử dụng các cơ chế đồng bộ như `synchronized`, `Lock`, hoặc các cấu trúc thread-safe (ví dụ: `ConcurrentHashMap`).

### **5.2 Deadlock (Bế tắc):**

* **Mô tả:** Hai hay nhiều thread chờ đợi lẫn nhau giải phóng tài nguyên mà mỗi thread đang giữ, dẫn đến việc không thread nào tiến triển được.
* **Hậu quả:** Hệ thống bị đứng, không thể tiếp tục thực hiện các công việc cần thiết.
* **Giải pháp:** Thiết kế thứ tự truy cập tài nguyên cố định, sử dụng timeout cho các thao tác chờ, và kiểm tra tình trạng deadlock.

### **5.3 Starvation (Thiếu đói):**

* **Mô tả:** Một thread hoặc một nhóm thread bị "bỏ rơi" và không được cấp đủ thời gian CPU do các thread khác có độ ưu tiên cao hơn luôn chiếm dụng tài nguyên.
* **Hậu quả:** Thread đó không thể hoàn thành công việc, dẫn đến hiệu suất hệ thống kém.
* **Giải pháp:** Điều chỉnh ưu tiên thread (priority) cẩn thận, sử dụng cơ chế cân bằng tài nguyên.

### **5.4 Livelock:**

* **Mô tả:** Các thread liên tục thay đổi trạng thái để tránh deadlock nhưng lại không tiến triển được công việc (chúng "vui chơi" với nhau nhưng không đạt được mục tiêu cuối cùng).
* **Hậu quả:** Hệ thống hoạt động không hiệu quả mặc dù không bị chặn hoàn toàn.
* **Giải pháp:** Thiết kế logic xử lý cẩn thận, kiểm tra và điều chỉnh các điều kiện đồng bộ.

### **5.5 Resource Exhaustion (Hết tài nguyên):**

* **Mô tả:** Tạo quá nhiều thread có thể dẫn đến tình trạng sử dụng bộ nhớ quá cao và tăng overhead do việc chuyển đổi context giữa các thread.
* **Hậu quả:** Ứng dụng bị chậm, có thể gây ra OutOfMemoryError hoặc làm giảm hiệu suất hệ thống.
* **Giải pháp:** Sử dụng Thread Pool (ví dụ: `ExecutorService`) để giới hạn số lượng thread chạy đồng thời, quản lý tài nguyên hợp lý.

### **5.6 IllegalThreadStateException:**

* **Mô tả:** Xảy ra khi cố gắng thực hiện thao tác không hợp lệ trên thread (ví dụ: gọi `start()` trên một thread đã được start rồi).
* **Hậu quả:** Lỗi runtime, làm dừng ứng dụng hoặc gây ra hành vi không mong đợi.
* **Giải pháp:** Kiểm tra trạng thái của thread trước khi thao tác, đảm bảo không khởi chạy lại thread đã kết thúc.

### **5.7 InterruptedException không được xử lý:**

* **Mô tả:** Khi một thread bị ngắt giữa chừng (thông qua `interrupt()`), nếu không xử lý ngoại lệ này đúng cách, có thể gây ra các trạng thái không ổn định.
* **Hậu quả:** Ứng dụng không phản hồi theo đúng yêu cầu ngắt, gây ra lỗi logic hoặc rò rỉ tài nguyên.
* **Giải pháp:** Bắt và xử lý `InterruptedException` đúng cách, thường là dừng công việc hoặc thực hiện các hành động dọn dẹp cần thiết.

### **5.8 ConcurrentModificationException:**

* **Mô tả:** Khi nhiều thread cố gắng thay đổi một cấu trúc dữ liệu không thread-safe (như `ArrayList`) đồng thời, gây ra lỗi khi duyệt qua danh sách.
* **Hậu quả:** Lỗi runtime khi duyệt hoặc sửa đổi collection.
* **Giải pháp:** Sử dụng các collection thread-safe (ví dụ: `CopyOnWriteArrayList`, `ConcurrentHashMap`) hoặc đồng bộ hóa truy cập.
