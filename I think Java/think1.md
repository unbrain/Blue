##### 讨论环境为 JDK 1.6

- Java 提供了循环控制（`while, do...while, for`），选择控制（`if, which`），转向控制（`break, continue, return`）和异常处理等几种流程控制语句

- `switch` 数据类型支持 `byte, short, char, int` (JDK1.7 有改变此处不讨论)

- [原码，反码与补码](https://www.cnblogs.com/zhangziqiu/archive/2011/03/30/ComputerCode.html)

- java % 与 mod 的区别（有无正负号）

  ```java
  int x = 7;
  double y = -5.0;
  System.out.println(x%y);//2.0 隐式自动转换 正负号取决于第一个值
  ```

  ​

- 注意 l 与 1

  ```java
  System.out.println("11");
  System.out.println("1l");
  ```

  ​

- 自增自减的优先级

  ```java
  int x = 1, y = 2, z = 3;
  y += z--/++x-x;//3/2——>1-2——>2-1
  System.out.print(y);//1
  ```

  ​

- 注意类型的隐式自动转换

  ```java
  int x = 4;
  System.out.println("value is " + ((x > 4)?88.8:8));//8.0
  ```

  ​

- `package` 语句只能放在除注释外的第一行的位置

- `finalize()` 析构函数 `System.gc()` 垃圾回收调用 `finalize()`

- Java 初始化默认值

  `boolean false`

  `int 0`

  `char  null`

- 用 `final` 修饰的方法不能被覆盖（重写），但是是可以重载的

- `Java` 的动态多态性是由覆盖实现的

- 对与类编写的时候最好写一个无参构造

  ​