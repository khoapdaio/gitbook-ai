# Java - Variable types

## Biến trong Java là gì ?

Biến trong Java à một vùng nhớ được đặt tên, dùng để lưu trử dữ liệu trong quá trình thực thi chương trình. Mỗi biến trong Java có một loại cụ thể, xác định kích thước và bố cục của bộ nhớ của biến; phạm vi của các giá trị có thể được lưu trữ trong bộ nhớ đó và tập hợp các hoạt động có thể được áp dụng cho biến đó

## Định nghĩa và khởi tạo giá trị cho biến&#x20;

Bạn phải khai báo tất cả các biến trước khi chúng có thể được sử dụng. Các biến Java được khai báo bằng cách chỉ định loại dữ liệu theo sau là tên biến. Để gán một giá trị, hãy sử dụng toán tử gán (=) theo sau là giá trị. Mỗi tuyên bố khai báo hoặc khởi tạo phải kết thúc bằng dấu chấm phẩy (;).

## Syntax

```
data_type variable [ = value][, variable [ = value] ...] ;
```

## Các loại biến Java

> * [Local variables](java-variable-types.md#id-1.-java-local-variable)
> * [Instance variables](java-variable-types.md#id-2.-java-instance-variables)
> * [Class/Static variables](java-variable-types.md#id-3.-java-class-static-variable)

### 1. Java local variables

> * Các biến cục bộ được khai báo trong các phương thức, hàm tạo hoặc khối.
> * Các biến cục bộ được tạo khi phương thức, hàm tạo hoặc khối được nhập và biến sẽ bị phá hủy khi nó thoát khỏi phương thức, hàm tạo hoặc khối.
> * Bộ điều chỉnh truy cập không thể được sử dụng cho các biến cục bộ.
> * Các biến cục bộ chỉ hiển thị trong phương thức, hàm tạo hoặc khối được khai báo.
> * Các biến cục bộ được thực hiện ở cấp độ ngăn xếp trong nội bộ.
> * Không có giá trị mặc định cho các biến cục bộ, vì vậy các biến cục bộ phải được khai báo và giá trị ban đầu nên được gán trước khi sử dụng đầu tiên.

{% tabs %}
{% tab title="Example 1: Variable's local scope with initialization" %}
```java
public class Test {
   public void pupAge() {
      int age = 0;
      age = age + 7;
      System.out.println("Puppy age is : " + age);
   }

   public static void main(String args[]) {
      Test test = new Test();
      test.pupAge();
   }
}
```

**Output**

```
Puppy age is: 7
```
{% endtab %}

{% tab title="Example 2: Variable's local scope without initialization" %}
```java
public class Test {
   public void pupAge() {
      int age;
      age = age + 7;
      System.out.println("Puppy age is : " + age);
   }

   public static void main(String args[]) {
      Test test = new Test();
      test.pupAge();
   }
}
```

**Output**

```
Test.java:4:variable number might not have been initialized
age = age + 7;
         ^
1 error
```
{% endtab %}
{% endtabs %}

### 2. Java Instance variables

> * Các biến thể hiện được khai báo trong một lớp, nhưng bên ngoài một phương thức, hàm tạo hoặc bất kỳ khối nào.
> * Khi một không gian được phân bổ cho một đối tượng trong Heap, một slot cho mỗi giá trị biến thể hiện được tạo.
> * Các biến thể hiện được tạo khi một đối tượng được tạo với việc sử dụng từ khóa 'mới' và bị phá hủy khi đối tượng bị phá hủy.
> * Các biến thể hiện giữ các giá trị phải được tham chiếu bằng nhiều phương thức, hàm tạo hoặc khối hoặc các phần thiết yếu của trạng thái đối tượng phải có mặt trong suốt lớp.
> * Các biến thể hiện có thể được khai báo ở cấp lớp trước hoặc sau khi sử dụng.
> * Trình sửa đổi truy cập có thể được đưa ra ví dụ như các biến.
> * Các biến thể hiện có thể nhìn thấy cho tất cả các phương thức, hàm tạo và chặn trong lớp. Thông thường, nên làm cho các biến này riêng tư (mức độ truy cập). Tuy nhiên, khả năng hiển thị cho các lớp con có thể được đưa ra cho các biến này với việc sử dụng các sửa đổi truy cập.
> * Các biến thể hiện có giá trị mặc định. Đối với các số, giá trị mặc định là 0, đối với booleans là sai và đối với các tham chiếu đối tượng, nó là null. Các giá trị có thể được chỉ định trong quá trình khai báo hoặc trong hàm tạo.
> * Các biến thể hiện có thể được truy cập trực tiếp bằng cách gọi tên biến bên trong lớp. Tuy nhiên, trong các phương thức tĩnh (khi các biến thể hiện được cung cấp khả năng truy cập), chúng nên được gọi bằng cách sử dụng tên đủ điều kiện. Objectreeference.variablename.&#x20;

**Example**

<pre class="language-java"><code class="lang-java"><strong>public class Person {
</strong>    //Instance variables
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

</code></pre>

### 3. Java Class/Static Variables

> * Các biến lớp còn được gọi là các biến tĩnh được khai báo với từ khóa tĩnh trong một lớp, nhưng bên ngoài một phương thức, hàm tạo hoặc một khối.
> * Sẽ chỉ có một bản sao của mỗi biến lớp cho mỗi lớp, bất kể có bao nhiêu đối tượng được tạo từ nó.
> * Các biến tĩnh hiếm khi được sử dụng ngoài việc được khai báo là hằng số. Hằng số là các biến được khai báo là công cộng/riêng tư, cuối cùng và tĩnh. Các biến không đổi không bao giờ thay đổi từ giá trị ban đầu của chúng.
> * Các biến tĩnh được lưu trữ trong bộ nhớ tĩnh. Rất hiếm khi sử dụng các biến tĩnh khác ngoài được khai báo cuối cùng và được sử dụng như là hằng số công cộng hoặc tư nhân.
> * Các biến tĩnh được tạo khi chương trình bắt đầu và phá hủy khi chương trình dừng lại.
> * Tầm nhìn tương tự như các biến thể hiện. Tuy nhiên, hầu hết các biến tĩnh được khai báo công khai vì chúng phải có sẵn cho người dùng của lớp.
> * Giá trị mặc định giống như các biến thể hiện. Đối với các số, giá trị mặc định là 0; Đối với Booleans, nó là sai; Và đối với tài liệu tham khảo đối tượng, nó là null. Các giá trị có thể được chỉ định trong quá trình khai báo hoặc trong hàm tạo. Ngoài ra, các giá trị có thể được gán trong các khối khởi tạo tĩnh đặc biệt.
> * Các biến tĩnh có thể được truy cập bằng cách gọi với tên lớp className.variablename.
> * Khi khai báo các biến lớp là cuối cùng tĩnh công khai, thì tên biến (hằng số) đều nằm trong trường hợp trên. Nếu các biến tĩnh không công khai và cuối cùng, cú pháp đặt tên giống như các biến thể và biến cục bộ.

```java
public class Person {
    //Instance variables
    private String name;
    private int age;
    // GENDER  is a contant
    public static final String GENDER = "Male";
    
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



