# Java -  OOP Concepts

Lập trình thủ tục là về các quy trình hoặc phương thức viết thực hiện các hoạt động trên dữ liệu, trong khi lập trình hướng đối tượng là về việc tạo các đối tượng có chứa cả dữ liệu và phương thức.

Lập trình hướng đối tượng có một số lợi thế so với lập trình thủ tục:

* OOP nhanh hơn và dễ thực hiện hơn&#x20;
* OOP cung cấp một cấu trúc rõ ràng cho các chương trình&#x20;
* OOP giúp giữ cho mã Java DRY "Don't repeat yourself" và làm cho mã dễ dàng hơn để duy trì, sửa đổi và gỡ lỗi&#x20;
* OOP có thể tạo các ứng dụng có thể tái sử dụng đầy đủ với ít mã hơn và thời gian phát triển ngắn hơn

<figure><img src="../../.gitbook/assets/image (48).png" alt=""><figcaption><p><a href="https://www.tutorialspoint.com/java/java_oops_concepts.htm">https://www.tutorialspoint.com/java/java_oops_concepts.htm</a></p></figcaption></figure>

## Các Khái niệm

* [Modifier](java-oop-concepts.md#modifie)
* [Class](java-oop-concepts.md#class)
* [Object](java-oop-concepts.md#object)
* [Inheritance](java-oop-concepts.md#inheritance)
* [Polymorphism](java-oop-concepts.md#polymorphism)
* [Abstraction](java-oop-concepts.md#absstraction)
* [Encapsulation](java-oop-concepts.md#encapsulation)

## Modifier

Từ khóa công khai là một công cụ sửa đổi truy cập, có nghĩa là nó được sử dụng để đặt mức truy cập cho các lớp, thuộc tính, phương thức và hàm tạo.

Chúng tôi chia các Modifier thành hai nhóm:

* Trình sửa đổi truy cập - Kiểm soát mức độ truy cập&#x20;
* Bộ điều chỉnh không truy cập - Không kiểm soát mức truy cập, nhưng cung cấp các chức năng khác

### Access Modifiers

Đối với **classes**, bạn có thể sử dụng `public` hoặc _default_:

<table><thead><tr><th width="100">Modifier</th><th>Description</th></tr></thead><tbody><tr><td>public</td><td>Lớp có thể được truy cập bởi các lớp khác</td></tr><tr><td><em>default</em></td><td>Lớp chỉ có thể truy cập bởi các lớp trong cùng một gói. Điều này được sử dụng khi bạn không chỉ định công cụ sửa đổi</td></tr></tbody></table>

Đối với các thuộc tính, phương thức và bộ xây dựng, bạn có thể sử dụng một trong những điều sau đây:

<table><thead><tr><th width="100">Modifier</th><th>Description</th></tr></thead><tbody><tr><td>public</td><td>Truy cập được từ <strong>mọi nơi</strong> (bất kỳ lớp nào trong cùng hoặc khác package).</td></tr><tr><td>private</td><td>Truy cập được <strong>chỉ trong cùng lớp</strong>.</td></tr><tr><td>default</td><td>Truy cập được trong <strong>cùng package</strong> (không khai báo access modifier).</td></tr><tr><td>protected</td><td>Truy cập được trong <strong>cùng package</strong> và <strong>lớp con</strong> (kế thừa từ lớp cha).</td></tr></tbody></table>

### Non-Access Modifier

<table><thead><tr><th width="189">Modifier</th><th>Description</th></tr></thead><tbody><tr><td><code>final</code></td><td>Lớp không thể được kế thừa bởi các lớp khác </td></tr><tr><td><code>abstract</code></td><td>Lớp không thể được sử dụng để tạo các đối tượng (để truy cập một lớp trừu tượng, nó phải được kế thừa từ một lớp khác. Bạn sẽ tìm hiểu thêm về kế thừa và trừu tượng trong các chương kế thừa và trừu tượng)</td></tr></tbody></table>

Đối với các thuộc tính và phương thức, bạn có thể sử dụng một trong những điều sau đây:

<table><thead><tr><th width="184">Modifier</th><th>Description</th></tr></thead><tbody><tr><td><code>final</code></td><td>Các thuộc tính và phương thức không thể được ghi đè/sửa đổi</td></tr><tr><td><code>static</code></td><td>Các thuộc tính và phương thức thuộc về lớp, thay vì một đối tượng</td></tr><tr><td><code>abstract</code></td><td>Chỉ có thể được sử dụng trong một lớp trừu tượng và chỉ có thể được sử dụng trên các phương thức. Phương pháp này không có phân thân, ví dụ abstract void run () ;. Cơ thể được cung cấp bởi lớp con (được thừa hưởng từ). </td></tr><tr><td><code>transient</code></td><td>Các thuộc tính và phương thức bị bỏ qua khi tuần tự hóa đối tượng chứa chúng</td></tr><tr><td><code>synchronized</code></td><td>Các phương thức chỉ có thể được truy cập bằng một luồng tại một thời điểm</td></tr><tr><td><code>volatile</code></td><td>Giá trị của một thuộc tính không được lưu trong bộ nhớ cach theo địa chỉ và luôn được đọc từ "bộ nhớ chính"</td></tr></tbody></table>

## Class

Class là một khuôn mẫu để tạo ra các đối tượng. Nó bao gồm các thuộc tính và phương phức mô tả hành vi của đối tượng

Các thành phần chính:

* Thuộc tính (Fields/Attributes): biến thành viên lưu trữ trạng thái của đối tượng
* Phương thức (Methods): Các hành động mà đối tượng có thể thực hiện
* Constructor: Phương thức đặc iệt dùng để khởi tạo đối tượng. Nó có thể tên trùng với tên lớp và không có kiểu trả về&#x20;

```java
public class Person {
    private String name;
    private int age;
    
    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    // Phương thức
    public void sayHello() {
        System.out.println("Hello, my name is " + name);
    }
}

```

## Object

### 1. Khái niệm

Object(Đối tượng) trong Java là một thực thể cụ thể được tạo ra từ một class(lớp).

### 2. Cách tạo từ Object trong java:

Sử dụng từ khoá new để cấp phát bộ nhớ và khởi tạo object

```java
ClassName objectName = new ClassName();  // Gọi constructor 
```

### 3. Vài trò của constructor

* Contructor là phương thức đặc biệt để khởi tạo object
* Nếu không có định nghĩa, java tự động tạo constructor mặc định(không tham số)

### 4. Đối tượng vào bộ nhớ&#x20;

* Khi tạo object bằng `new`, bộ nhớ được cấp phát trong **Heap Memory**.
* Biến tham chiếu (ví dụ: `myDog`, `student1`) lưu trữ địa chỉ của object trong heap.
* Java tự động quản lý bộ nhớ bằng **Garbage Collector** (dọn rác) khi object không còn được tham chiếu.

## Inheritance

Kế thừa là một quá trình cho phép một class (sub - class) được thừa kế thuộc tính và phương thức của một class khác (super - class) định nghĩa. Với việc sử dụng kế thừa, thông tin được quản lý theo thứ tự phân cấp.

```java
class Vehicle {
  protected String brand = "Ford";        // Vehicle attribute
  public void honk() {                    // Vehicle method
    System.out.println("Tuut, tuut!");
  }
}

class Car extends Vehicle {
  private String modelName = "Mustang";    // Car attribute
  public static void main(String[] args) {

    // Create a myCar object
    Car myCar = new Car();

    // Call the honk() method (from the Vehicle class) on the myCar object
    myCar.honk();

    // Display the value of the brand attribute (from the Vehicle class) and the value of the modelName from the Car class
    System.out.println(myCar.brand + " " + myCar.modelName);
  }
}
```

## Polymorphism

Đa hình có nghĩa là "nhiều hình thái", tức là Đa hình cho phép các đối tượng thuộc các lớp khác nhau xử lý cùng một hành động theo cách riêng cưa chúng

### Các loại đa hình trong java

1. Đa hình lúc biên dịch (Compile time polymorphism)

**Cơ chế**: Overloading nạp chồng phương thức

**Đặc điểm:**

* Cùng tên phương thức, nhưng khác tham số (số lượng, kiểu dữ liệu, vị trí)
* Xác định phương thức cần gọi ngay khi biên dịch

```java
public class Calculator {
    // Overloading phương thức add()
    public int add(int a, int b) {
        return a + b;
    }
    
    public double add(double a, double b) {
        return a + b;
    }
    
    public String add(String a, String b) {
        return a + b;
    }
}
```

2. Đa hình lúc thực thi (runtime polymorphism)

**Cơ chế**: Overriding(ghi đè phương thức)

**Đặc điểm:**&#x20;

* Phương thức của lớp con ghi đè phương thức lớp cha
* Xác định phương thức cần gọi khi chạy chương trình (Dựa trên đối tượng thực tế)

```java
// Lớp cha
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

// Lớp con
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks: Gâu gâu!");
    }
}

class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Cat meows: Meow meow!");
    }
}

// Sử dụng
public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Dog();  // Upcasting
        Animal animal2 = new Cat();
        
        animal1.makeSound();  // Output: "Dog barks: Gâu gâu!"
        animal2.makeSound();  // Output: "Cat meows: Meow meow!"
    }
}
```

### Lợi ích&#x20;

* Tái sử dụng code: dùng chung interface cho nhiều đối tượng&#x20;
* Dễ mở rộng: thêm lớp mới không sửa code hiện có
* Giảm độ phức tạp: quản lý đối tượng thông qua lớp cha/ interface

## Absstraction

**Trừu tượng (Abstraction)** là một trong **4 tính chất cơ bản** của lập trình hướng đối tượng (OOP). Nó cho phép ẩn đi các chi tiết phức tạp bên trong và chỉ hiển thị những **tính năng cần thiết** ra bên ngoài. Trừu tượng giúp tập trung vào **hành vi** của đối tượng thay vì cách thức triển khai cụ thể.

### Các implementation trừu tượng trong Java

1. Abstract Class (Lớp trừu tượng)

**Đặc điểm**:

* Khai báo bằng từ khóa `abstract`.
* Có thể chứa **phương thức trừu tượng** (không có thân hàm) và **phương thức cụ thể** (có thân hàm).
* Không thể tạo đối tượng trực tiếp từ lớp trừu tượng.

```java
// Lớp trừu tượng
abstract class Animal {
    // Phương thức trừu tượng (không có thân hàm)
    abstract void makeSound();

    // Phương thức cụ thể (có thân hàm)
    void sleep() {
        System.out.println("Zzz...");
    }
}

// Lớp con kế thừa
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Gâu gâu!");
    }
}

// Sử dụng
public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.makeSound();  // Output: "Gâu gâu!"
        dog.sleep();      // Output: "Zzz..."
    }
}
```



2. Interface (Giao diện)

**Đặc điểm**:

* Khai báo bằng từ khóa `interface`.
* Chỉ chứa **phương thức trừu tượng** (từ Java 8, có thể thêm phương thức mặc định `default` và phương thức tĩnh `static`).
* Một lớp có thể triển khai nhiều interface (đa kế thừa)

```java
// Interface
interface Drawable {
    void draw();  // Phương thức trừu tượng
}

// Lớp triển khai
class Circle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Vẽ hình tròn");
    }
}

// Sử dụng
public class Main {
    public static void main(String[] args) {
        Drawable circle = new Circle();
        circle.draw();  // Output: "Vẽ hình tròn"
    }
}
```

### So sánh implementation

| Abstract Class                  | Interface                                       |
| ------------------------------- | ----------------------------------------------- |
| Có thể chứa phương thức cụ thể. | Chỉ chứa phương thức trừu tượng (trước Java 8). |
| Hỗ trợ đơn kế thừa.             | Hỗ trợ đa kế thừa.                              |
| Có thể chứa biến instance.      | Chỉ chứa hằng số (`public static final`).       |
| Dùng từ khóa `abstract`.        | Dùng từ khóa `interface`.                       |

### Lợi ích của trừu tượng

1. **Giảm độ phức tạp**: Ẩn đi chi tiết triển khai, chỉ hiển thị chức năng cần thiết.
2. **Tái sử dụng code**: Các lớp con kế thừa và triển khai phương thức trừu tượng.
3. **Dễ bảo trì**: Thay đổi triển khai bên trong mà không ảnh hưởng đến code bên ngoài.

## Encapsulation

Đóng gói giúp **ẩn giấu thông tin** và **bảo vệ dữ liệu** của đối tượng bằng cách kết hợp dữ liệu (biến) và phương thức (hành vi) vào trong một lớp, đồng thời kiểm soát quyền truy cập vào dữ liệu thông qua các [**access modifier**.](java-oop-concepts.md#modifier)

### **Lợi Ích Của Đóng Gói**

1. **Bảo vệ dữ liệu**: Ngăn chặn truy cập trái phép hoặc thay đổi dữ liệu không mong muốn.
2. **Tính toàn vẹn**: Đảm bảo dữ liệu luôn hợp lệ thông qua các phương thức setter.
3. **Dễ bảo trì**: Thay đổi cách triển khai bên trong mà không ảnh hưởng đến code bên ngoài.
4. **Tính linh hoạt**: Có thể thêm logic kiểm tra hoặc xử lý trong getter/setter.

### **Lưu Ý Quan Trọng**

* **Access Modifier**: Sử dụng `private` để đóng gói dữ liệu, `public` cho các phương thức truy cập.
* **Getter/Setter**: Cung cấp quyền truy cập có kiểm soát vào dữ liệu.
* **Tính toàn vẹn**: Thêm logic kiểm tra trong setter để đảm bảo dữ liệu hợp lệ.





