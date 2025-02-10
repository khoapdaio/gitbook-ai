# Java - Data type

Kiểu dữ liệu Java xác định phạm vi loại và giá trị của dữ liệu cho các loại biến, hằng số, tham số phương thức, loại trả về, loại dữ liệu khác nhau cho trình biên dịch về loại dữ liệu được lưu trữ và bộ nhớ cần thiết. Để lưu trữ và thao tác cá loại dữ liệu khác nhau, tất cả các biến phải có các loại dữ liệu được chỉ định

Dựa trên loại dữ liệu của một biến, hệ điều hành phân bố bộ nhớ và quyết định những gì có thể được lưu trữ trong bộ nhớ dành riêng. Do đó bằng cách gán các loại dữ liệu khác nhau cho các biến, bạn có thể lưu trữ số nguyên, số thập phân hoặc ký tự trong các biến này.

Có 2 loại kiểu dữ liệu chính&#x20;

> * [Các loại dữ liệu nguyên thuỷ](java-data-type.md#java-primitive-data-types)
> * [Các loại dữ liệu  tham chiếu/đối tượng](java-data-type.md#java-non-primitive-reference-object-data-types)

## Java Primitive Data Types (Các loại dữ liệu nguyên thuỷ)

Các loại dữ liệu nguyên thủy được xác định trước bởi ngôn ngữ và được đặt tên bởi một từ khóa. Có tám loại dữ liệu nguyên thủy được Java hỗ trợ

| Data Type | Description                                                                       |
| --------- | --------------------------------------------------------------------------------- |
| `byte`    | Stores whole numbers from -128 to 127                                             |
| `short`   | Stores whole numbers from -32,768 to 32,767                                       |
| `int`     | Stores whole numbers from -2,147,483,648 to 2,147,483,647                         |
| `long`    | Stores whole numbers from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| `float`   | Stores fractional numbers. Sufficient for storing 6 to 7 decimal digits           |
| `double`  | Stores fractional numbers. Sufficient for storing 15 to 16 decimal digits         |
| `boolean` | Stores true or false values                                                       |
| `char`    | Stores a single character/letter or ASCII values                                  |

Example

```java
public class JavaTester {
   public static void main(String args[]) {

      byte byteValue1 = 2;
      byte byteValue2 = 4;
      byte byteResult = (byte)(byteValue1 + byteValue2);

      System.out.println("Byte: " + byteResult);

      short shortValue1 = 2;
      short shortValue2 = 4;
      short shortResult = (short)(shortValue1 + shortValue2);

      System.out.println("Short: " + shortResult);

      int intValue1 = 2;
      int intValue2 = 4;
      int intResult = intValue1 + intValue2;

      System.out.println("Int: " + intResult);

      long longValue1 = 2L;
      long longValue2 = 4L;
      long longResult = longValue1 + longValue2;

      System.out.println("Long: " + longResult);

      float floatValue1 = 2.0f;
      float floatValue2 = 4.0f;
      float floatResult = floatValue1 + floatValue2;

      System.out.println("Float: " + floatResult);

      double doubleValue1 = 2.0;
      double doubleValue2 = 4.0;
      double doubleResult = doubleValue1 + doubleValue2;

      System.out.println("Double: " + doubleResult);

      boolean booleanValue = true;

      System.out.println("Boolean: " + booleanValue);

      char charValue = 'A';

      System.out.println("Char: " + charValue);     
   }
}
```

## Java Non-Primitive (Reference/Object) Data Types

Các loại dữ liệu không nguyên thủy không được xác định trước. Các loại dữ liệu tham chiếu được tạo bằng các hàm tạo xác định của các lớp. Chúng được sử dụng để truy cập các đối tượng. Các biến này được tuyên bố là một loại cụ thể không thể thay đổi

> * Chuỗi: Chuỗi là một lớp trong Java và nó đại diện cho các chuỗi ký tự.&#x20;
> * Mảng: Mảng được tạo với sự trợ giúp của các loại dữ liệu nguyên thủy và lưu trữ nhiều giá trị cùng loại.&#x20;
> * Các lớp: Các lớp là các loại dữ liệu do người dùng xác định và bao gồm các biến và phương thức.&#x20;
> * Interfaces Các giao diện là các loại trừu tượng được sử dụng để chỉ định một tập hợp các phương thức.

```java
// Creating an object of 'String' class
String myString = new String("Hello, World!");
```

