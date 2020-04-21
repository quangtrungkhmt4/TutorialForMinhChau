# Lập trình hay vãi beep :D 

Kiến thức cơ bản và cú pháp khai báo trong JAVA

## Biến trong Java(Variables)

Biến là nơi chứa giá trị trong khi chương trình JAVA thực thi, biến sẽ luôn đi kèm với một kiểu dữ liệu tương ứng.

Ta có thể hiểu đơn giản là: khi chương trình chạy có những giá trị được sử dụng trong chương trình chúng sẽ được lưu trong bộ nhớ RAM của máy tính, để ta có thể tương tác được với giá trị đó thì ta sẽ gán cho giá trị đó một cái nhãn với tên là gì đó và khi cần sử dụng ta chỉ cần gọi đến cái tên nhãn đó, ở đây cái nhãn ta gán cho giá trị chính là biến còn tên cái nhãn chính là tên biến mà ta đặt.

```java
// Cú pháp khai báo biến
<Kiểu_dữ_liệu> <Tên_biến> = <Giá_trị_cần_gán>;
int number = 5; // tạo ra một biến có kiểu dữ liệu là số nguyên, tên là number và có giá trị là 5
```

Có 3 loại biến trong Java: Local, Instance, Static
* Biến Local là các biến được khai báo trong một phương thức(method) và phạm vi sử dụng của biến đó chỉ trong phương thức đó.
```Java
private void doSomething(){
   int number = 5; 
   //biến number được gọi là biến local vì phạm vi sử dụng của nó chỉ trong phương thức doSomething()
}
```
* Biến Instance là những biến được khai báo trong một class bên ngoài phương thức và không có từ khóa static, phạm vi sử dụng của nó là ở toàn bộ class mà nó được khai báo.
```java
public class Persion{
   int age = 10;
   // biến age là biến instance vì phạm vi sử dụng của nó ở toàn bộ class Person

   doSomething(){}
}
```
* Biến Static là biến được khai báo với từ khóa static, ta có thể sử dụng biến này ở mọi class. Giá trị của biến static được khởi tạo một lần duy nhất lúc chương trình bắt đầu chạy.
```java
public class Person{
   public static int age = 5;
   // biến age là một biến static và ta có thể sử dụng nó ở các class khác
}
```

## Kiểu dữ liệu trong Java
Kiểu dữ liệu trong Java nó thể hiện loại giá trị lưu trữ và kích thước của giá trị đó. Có hai loại kiểu dữ liệu là:
* Kiểu dữ liệu nguyên thủy(Primitive data types) bao gồm các kiểu dữ liệu sau: boolean, char, byte, short, int, long, float và double.

Ví dụ về khai báo kiểu số nguyên
```java
   //kiểu số nguyên
   int number = 10;
   long longNumber = 1000000L;
   // vậy tại sao lại cần đến nhiều kiểu dữ liệu số nguyên đến vậy, sự khác biệt nằm ở giá trị min và max 
   // mà chúng có thể lưu trữ. 
   // với int min = -2,147,483,648 và max = 2,147,483,647
   // với long min = -9,223,372,036,854,775,808 và max = 9,223,372,036,854,775,807
```
Ví dụ về khai báo kiểu số thập phân
```java
   //kiểu số thập phân
   float number = 4.6f;
   double doubleNumber = 188888.44;
   // cũng như với kiểu số nguyên, kiểu thập phân cũng có nhiều loại và sự 
   // khác biệt giữa chúng vẫn là về giá trị min và max mà chúng có thể lưu trữ
```
Ví dụ về khai báo kiểu ký tự
```java
   char character = 'k';
   // mỗi ký tự sẽ được khai báo trong dấu nháy đơn ''
```
Ví dụ khai báo kiểu logic
```java
   boolean isRunning = true;
   boolean isMale = false;
   // kiểu dữ liệu logic sẽ bao gồm 2 giá trị: true và false
```
## Toán tử trong Java(Operators)
Toán tử trong Java là một ký tự được dùng để thực hiện các phép tính.
Một số toán tử thông dụng trong Java là:
* Toán tử một ngôi
1. Toán tử cộng (+): toán tử này để thể hiện một số dương, nhưng bình thường khi khai báo một số dương ta không cần khai báo toán tử này nên ta sẽ ít gặp toán tử này.
```java
   int number = +5;
```
2. Toán tử trừ (-): toán tử này ngược lại với toán tử cộng, nó để thể hiện một số âm
```java
   int number = -5;
```
3. Toán tử tăng (++): toán tử này để tăng giá trị của toán hạng lên 1 đơn vị
```java
   int number = 5;
   number++;
   //output: number = 6
```
4. Toán tử giảm (--): toán tử này để giảm giá trị của toán hạng đi 1 đơn vị
```java
   int number = 5;
   number--;
   //output: number = 4
```
5. Toán tử phủ định logic (!): toán tử này sẽ đảo được giá trị của biểu thức logic
```java
   boolean isMale = false;
   //output: !number = true
```
[*] Với toán tử ++ và -- sẽ có trường hợp toán tử đứng trước toán hạng và đứng sau toán hạng như sau: 
```java
   int number = 5;
   number++;
   ++number;
   // khi toán tử và toán hạng đứng đọc lập một mình như trên thì việc toán tử đứng trước hay đứng sau toán 
   // hạng không quan trọng, kết quả vẫn làm thay đổi giá trị của toán hạng đi 1 đơn vị. Nhưng trường hợp 
   // toán tử và toán hạng không đứng một mình mà tham gia vào một biểu thức hay câu lệnh khác ta sẽ chia 
   // hai trường hợp như sau:

   // 1. Trường hợp toán tử đứng trước toán hạng
   int count = 5;
   int result = 5 + ++count;
   // khi này kết quả sẽ là 11 do toán tử ++ sẽ được thực hiện trước rồi mới thực hiện biểu thức tính 
   // result.
   // 2. Trường hợp toán tử đứng sau toán hạng
   int total = 10; 
   int temp = 5 + total++;
   // khi này kết quả sẽ là 15 do biểu thức sẽ thực hiện trước rồi mới thực thi toán tử ++
``` 
* Toán tử số học
Toán tử số học bao gồm những toán tử giống như các phép toán trong toán học như: +, -, *, /, %(chia dư)
```java
   int firstNumber = 10;
   int secondNumber = 5;
   System.out.println(firstNumber + secondNumber); // output: 15
   System.out.println(firstNumber - secondNumber); // output: 5
   System.out.println(firstNumber * secondNumber); // output: 50
   System.out.println(firstNumber / secondNumber); // output: 2
   System.out.println(firstNumber % secondNumber); // output: 0
```
* Toán tử quan hệ
Toán tử quan hệ là một phép so sánh các biểu thức với nhau để trả về một kết quả boolean.
Ta có các toán tử quan hệ sau: ==, !=, <, <=, >, >=
```java
   int firstNumber = 10;
   int secondNumber = 20;

   System.out.println(firstNumber == secondNumber);     //output: false
   System.out.println(firstNumber != secondNumber);     //output: true
   System.out.println(firstNumber <= secondNumber);     //output: true
   System.out.println(secondNumber / firstNumber == 2); //output: true
   System.out.println(firstNumber % secondNumber == 0); //output: true
```
* Toán tử điều kiện
Toán tử điều kiện so sánh các biểu thức mang giá trị true và false với nhau.
Có 2 toán tử điều kiện thông dụng là && và ||
```java
   int number = 5;
   int age =  23;
   System.out.println(number == 5 && age == 23); //output: true
   // trường hợp này phải thỏa mãn đủ 2 điều kiện thì mới true

   System.out.println(number != 10 || age < 20); //output: false
   // trường hợp này chỉ cần thỏa mãn 1 trong hai điều kiện là true
```
## Cấu trúc điều kiện trong Java(if - else/if - else if - else)



## License
BenjaminLe - Lê Quang Trung